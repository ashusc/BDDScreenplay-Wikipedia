pipeline {
    agent any
    stages {
	stage('Clean Stage') {
            steps {
                echo 'Cleaning the workspace....'
                withMaven(maven: 'mvn_3_6_0'){
		    if (isUnix()) {
                        sh "mvn clean"
                    } else {
                        bat(/mvn clean/)
                    }
                }
            }
        }
        stage('VerifyAndBuild Stage') {
            steps {
                echo 'Compiling and initiating tests....'
                withMaven(maven: 'mvn_3_6_0'){
		    if (isUnix()) {
                        sh "mvn install"
                    } else {
                        bat(/mvn install/)
                    }
                }
            }
        }
        stage('Deploy Stage') {
            steps {
                echo 'Now Deploying....'
                withMaven(maven: 'mvn_3_6_0'){
		    if (isUnix()) {
                        sh "echo Deploy the reports now on the unix machine"
                    } else {
                        bat(/echo 'Deploy the reports now on the unix machine'/)
                    }
                }
            }
        }
    }
}