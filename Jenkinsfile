pipeline {
	agent any

  stages {
	  stage('Building'){
		  steps{
	    
	cmakeBuild buildDir: 'build', installation: 'InSearchPath', steps: [[withCmake: true]]
		   }  }
	  stage('Cppcheck'){
		  steps{
			  publishCppcheck allowNoReport: true, pattern: 'cppcheck-result.xml'
		  }}
  }
}

