pipeline {

agent any

tools{
	maven 'Maven'
}

	stages{
		stage('checkout')
		{
		steps{
			git branch:'main',url:'https://github.com/prasadmv-collab/selex.git'
		}
		}
		
		stage('Build')
		{
		steps{
		
			sh 'mvn clean package'
			}
			}
	
	stage('Test')
	{
	steps{
		sh 'mvn test'
		}
		}
		
		}
	post{
		always{
		
			junit '**/target/surefire-reports/*.xml'
			
			}
			
			success{
				echo 'Build successful'
				}
				
			failure{
			
				echo 'Build failure'
				}
			}
		}
