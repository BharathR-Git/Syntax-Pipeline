pipeline {
  agent any
  
    stages {
    
      stage('build C-Project') {
        steps {
          git 'https://github.com/BharathR-Git/Jenkins-C-Project.git'
          sh 'make'
              }
	 }
			
	stage ('build Java-Project){
	  steps {
	    git 'https://github.com/BharathR-Git/Jenkins-Java-Project.git'
	    sh 'mvn clean install'
	         }
	     }
	}
 }
