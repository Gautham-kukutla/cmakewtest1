pipeline {
	agent any

  stages {
	  stage('Building and gtesting'){
		  steps{
	    
	cmakeBuild buildDir: 'build', installation: 'InSearchPath', steps: [[withCmake: true]]
	
		   }  }
	  stage('Cppcheck'){
		  steps{
			   if (isUnix()) {
    				sh "cppcheck  --xml --xml-version=2 . 2> cppcheck.xml"
} if {
			  bat "cppcheck  --xml --xml-version=2 . 2> cppcheck.xml"
			   }
			  publishCppcheck allowNoReport: true, pattern: '**/cppcheck.xml'
		  }}
	  
  	stage('gtest'){
		  steps{
			  if (isUnix()) {
				  sh "cd build/test/debug && mytest --gtest_output=xml:testresults.xml"
				  if(iswindows(){
			  bat "cd build/test/debug && mytest --gtest_output=xml:testresults.xml"
				  }
		  }}
  }}

