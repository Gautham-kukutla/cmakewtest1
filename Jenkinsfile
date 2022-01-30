pipeline {
	agent any

  stages {
	  stage('Building and gtesting'){
		  steps{
	    
	cmakeBuild buildDir: 'build', installation: 'InSearchPath', steps: [[withCmake: true]]
	
		   }  }
	  stage('Cppcheck'){
		  steps{
			  bat "cppcheck  --xml --xml-version=2 . 2> cppcheck.xml"
			  publishCppcheck allowNoReport: true, pattern: '**/cppcheck.xml'
		  }}
	  
  	stage('gtest'){
		  steps{
			  bat "cd build/test/debug && mytest input.txt --gtest_output=xml:testresults.xml"
			  
		  }}
  }}

