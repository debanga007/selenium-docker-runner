pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Running the Tests"){
			steps{
				bat "docker-compose up search-module1 book-flight-module2"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**' 
			bat "docker-compose down"
		}
	}
}