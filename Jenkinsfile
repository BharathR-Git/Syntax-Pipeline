pipeline {
	agent any
	
		stages {
		
			stage('STAGE 1'){
				step {
					sh 'sleep 10'
					}
			}
			
			stage('STAGE 2'){
				step {
					sh 'sleep 10'
				}
			}
		
			stage('STAGE 3'){
				step {
					sh 'sleep 10'
				}
			}
			
			stage {'STAGE 4'}{
				step {
					sh - 'sleep 10'
				}
			}
		
		}
		}
}
