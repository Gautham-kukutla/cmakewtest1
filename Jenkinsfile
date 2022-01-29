pipeline {
	agent any

  stages {
	  stage('Building and gtesting'){
		  steps{
	    
	cmakeBuild buildDir: 'build', installation: 'InSearchPath', steps: [[withCmake: true]]
	
		   }  }
	  stage('Cppcheck'){
		  steps{
			  bat "cppcheck --enable=all --inconclusive --xml --xml-version=2 . 2> cppcheck.xml"
			  publishCppcheck allowNoReport: true, pattern: '**/cppcheck.xml'
		  }}
	  stage('gtest'){
		  steps{
			  bat 'cd build && test/sample_tests --gtest_output="xml:testresults.xml"'
			  junit allowEmptyResults: true, skipMarkingBuildUnstable: true, testResults: '**/testresults.xml'
			  
		  }}}}

