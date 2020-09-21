pipeline {
  agent none
	
	stages {
		stage ('C-Project and Java-Project') {
			parallel {
				stage('build C-Project') {
					agent { label 'label1'}
					steps {
						git 'https://github.com/BharathR-Git/Jenkins-C-Project.git'
						sh '''
						sleep 10
						echo "This is C-Project"
						make
						'''
					}
				}
				stage ('build Java-Project1'){
					agent { label 'label2'}
					steps {
						git 'https://github.com/BharathR-Git/Jenkins-Java-Project.git'
						sh '''
						sleep 10
						echo "This is Java-Project"
						mvn clean package
						curl -v -u admin:admin -T /home/ec2-user/workspace/Jenkins-Java-Project/target/hello-world-war-1.0.0.war http://3.135.248.131:8080/manager/html/undeploy?path=/Jenkins-Java-Project
						'''
					}
				}		
			}
		}
		stage ('build Java-Project2'){
			agent {label 'master'}
			steps {
				git 'https://github.com/BharathR-Git/Java-Project.git'
				sh '''
				sleep 10
				echo "This is Java-Project"
				mvn clean install
				'''
			}
		}
	}
}

