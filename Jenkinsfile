pipeline {
  agent none
  
    stages {
    
      stage('build C-Project') {
	agent { label 'label1'}
         steps {
          git 'https://github.com/BharathR-Git/Jenkins-C-Project.git'
          sh 'make'
              }
	 }
			
	stage ('build Java-Project'){
	 agent { label 'label2'}
	  steps {
	    git 'https://github.com/BharathR-Git/Jenkins-Java-Project.git'
	    sh 'mvn clean install'
	         }
	     }
	}
 }
