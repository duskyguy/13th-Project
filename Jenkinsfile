 pipeline {	
	agent any
	environment { 
        CC = 'clang'
    }
	Tools {
	          maven 'localmaven'
	         }
	stages{
	stage('Build'){
	steps {
	sh 'mvn clean package'
	}
	steps {
	sh 'printenv'
	}
	post {
	success {
	echo 'Now Archiving...'
	#archiveArtifacts artifacts: '**/target/*.war'
	
	}
	}
	}
	stage ('Deploy to Staging'){
	steps {
	build job: 'Deploy-to-staging'
	}
	}
	}
	}

