pipeline {
	agent any

	// environment {
	// 	mavenHome = toWol 'jenkins-maven'
	// }

	// tools {
	// 	jdk 'java-17'
	// }

	stages {

		stage('Compose up'){
			steps {
				sh 'docker-compose up -d'     
    			echo 'Docker-compose-build Build Image Completed'   
			}
		}

		// stage('Deploy') {
		// 	steps {
		// 	    bat "mvn jar:jar deploy:deploy"
		// 	}
		// }
	}
}