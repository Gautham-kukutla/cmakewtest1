pipeline {
	agent any

  stages {
	  stage('Building and gtesting'){
				  
		  steps{
	    
	cmakeBuild buildDir: 'build', installation: 'InSearchPath', steps: [[withCmake: true]]
	
		   }  }
	  stage('Cppcheck'){
		 
		  steps{
			  script{
			   if (isUnix()) {
    				sh "cppcheck  --xml --xml-version=2 . 2> cppcheck.xml"
} else {
			  bat "cppcheck  --xml --xml-version=2 . 2> cppcheck.xml"
			   }}
			  publishCppcheck allowNoReport: true, pattern: '**/cppcheck.xml'
		  }}
	  
  	stage('gtest'){
		
		  steps{
			  script{
			  if (isUnix()) {
				  sh "cd /var/lib/jenkins/workspace/cmaketestl1/build/test && ./mytest set +e"
			  }
				  else{
			  bat "cd build/test/debug && mytest set +e"
			  
				  }}
		  }}
  }}

