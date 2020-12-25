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
			stage('Test'){
				steps{
					echo "Test"
				}
			}
			stage('Integration Test'){
				steps{
					echo "Integration Test"
				}
			}
		}
}
