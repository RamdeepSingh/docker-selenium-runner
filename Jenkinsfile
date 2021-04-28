pipeline {
    agent any
    stages {
		stage('Setting up Grid') {
            steps {
                bat "docker-compose up -d ramdeep_hub ramdeep_chrome ramdeep_firefox"
            }
        }
        stage('Run Test') {
            steps {
                bat "docker-compose up duckduckgo-searchResults-module newtours-flightBooking-module"
            }
        }
        stage('Bring grid down') {
            steps {
                bat "docker-compose down"
            }
        }
    }
}