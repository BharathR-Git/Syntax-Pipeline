pipeline {
	agent none
	
		stages {
		
			stage('STAGE 1'){
				agent {label 'label2'}
					steps {
						sh 'sleep 10'
						echo 'run in slave2'
						}
			}
			
			stage('STAGE 2'){
				agent {label 'master'}
					steps {
						sh 'sleep 10'
						echo 'run in Master'
					}
			}	
		
			stage('STAGE 3'){
				agent {label 'label2'}
					steps {
						sh 'sleep 10'
						echo 'run in slave2'
						
					}
			}
			
			stage ('STAGE 4'){
				agent {label 'master'}
					steps {
						sh 'sleep 10'
						echo 'run in Master'
					}
			}
		
		}
}
