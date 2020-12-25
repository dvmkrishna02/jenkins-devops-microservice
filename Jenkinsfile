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
	environment {
		//dockerHome = tool 'Docker'
		mavenHome = tool 'myMaven'
		PATH = "$mavenHome/bin:$PATH"
	}
		stages{
			stage('Checkout'){
				steps{
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH - $PATH"
					echo "BUILD ID - $env.BUILD_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
					echo "BUILD_URL - $env.BUILD_URL"
				}
			}
			stage('Compile') {
				steps {
					sh 'mvn clean compile'
				}
			}
			stage('Test'){
				steps {
					sh 'mvn test'
				}
			}
			stage('Integration Test'){
				steps{
					sh 'mvn failsafe:integration-test failsafe:verify'
				}
			}
			stage('Package'){
				steps {
					sh 'mvn package -DskipTests'
				}
			}
			stage('Build docker image') {
				steps {
					script {
						dockerImage =  docker.build("100288/currency-exchange-devops:${env.BUILD_TAG}")
					}
				}
			}
			stage('Push docker image') {
				steps {
					script {
						docker.withRegistry('', 'dockerhub'){
							dockerImage.push();
							dockerImage.push('latest');
						}
					}
				}
			}
		}
}
