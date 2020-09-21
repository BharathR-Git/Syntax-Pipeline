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
						mvn clean install
						cd /var/lib/jenkins/workspace/Jenkins-Pipeline/target
						scp *.war /home/ec2-user/apache-tomcat-9.0.38/webapps
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

