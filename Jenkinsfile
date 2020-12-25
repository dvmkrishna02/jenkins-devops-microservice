//SCRIPTED PIPELINE

/*node {
	stage('Build') {
		echo "Build"
	}
	stage('Test') {
		echo "Test"
	}
}*/

//DECLARATIVE PIPELINE

pipeline {
	agent any
		stages{
			stage('Build'){
				steps{
					echo "Build"
				}
			}
		}
		stages{
			stage('Test'){
				steps{
					echo "Test"
				}
			}
		}
		stages{
			stage('Integration Test'){
				steps{
					echo "Integration Test"
				}
			}
		}
}
