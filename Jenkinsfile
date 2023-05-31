pipeline {
    agent any
    stages {
		
		
		//Stage - Clean
        stage('Clean') {
            steps {
				tools {
					maven 'MAVEN_HOME'
                sh 'mvn clean'
					 }
				  }
		}

		//Stage - Compile
		stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
		

		//Stage - System Test
		stage('System Test') {
            steps {
				git url: 'https://github.com/umangagarwalit/SeleniumMavenJenkins.git'
            	sh 'mvn -Dtest=HandleSeleniumTest test'
            }
        }
	

		//Stage - BDD Test
		stage('BDD Test') {
            steps {
				
				git url: 'https://github.com/umangagarwalit/SeleniumCucumberMavenJenkins.git'
            	sh 'mvn -Dtest=TestRunner test'
            }
        }
		
		
    }
}