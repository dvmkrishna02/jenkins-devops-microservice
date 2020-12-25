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
	agent any{
		stages{
			stage('Build'){
				echo "Build"
			}
		}
		stages{
			stage('Test'){
				echo "Test"
			}
		}
		stages{
			stage('Integration Test'){
				echo "Integration Test"
			}
		}
	}
}
