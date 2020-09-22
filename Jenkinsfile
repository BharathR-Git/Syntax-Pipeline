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
						'''
					}
				}
				stage ('deploy to tomcat'){
					agent { label 'label2'}
					steps {
					sshagent(['69a21f78-391e-4e63-a4a8-43296beb20d9']) {
						sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@3.128.32.167:/home/ec2-user/apache-tomcat-9.0.38/webapps'

						}
					}
				}		
			}
		}
		stage ('build Java-Project2'){
			agent {label 'label2'}
			steps {
				git 'https://github.com/BharathR-Git/Java-Project.git'
				sh '''
				sleep 10
				echo "This is Java-Project"
				mvn clean install
				curl -v -u admin:admin -T /home/ec2-user/workspace/Java-Project/target/mvn-hello-world.war http://3.128.32.167:8080/manager/text/deploy?path=/Java-Project
				'''
			}
		}
	}
}
