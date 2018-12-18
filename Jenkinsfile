pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    stages {
        stage('Build') {
            steps {
                echo 'Build'
            }
        }
        stage('Deploy to Test') {
            steps {
                echo 'Deploy to Test'
                script {
				    def request = ChangeRequest shortDescription:'Deploy to Test',type:'Standard',category:'Other',impact:'3 - Low',risk:'Moderate',priority:'4 - Low',ci:'AS400'
				    createChangeRequest changeRequest: request
                }
            }
        }
        stage('Smoke Test') {
            steps {
                echo 'Smoke Test'
            }
        }
        stage('Integration Test') {
            steps {
                echo 'Integration Test'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production'
                script {
				    def start = new Date()
				    	    
				    sleep 30
				    
				    def end = new Date()
				    def request = ChangeRequest shortDescription:'Deploy to Production',type:'Standard',category:'Other',impact:'3 - Low',risk:'Moderate',priority:'4 - Low',ci:'AS400',workStartDate:start,workEndDate:end
					createChangeRequest changeRequest: request
                }
            }
        }
        stage('Production Smoke Tests') {
            steps {
                echo 'Production Smoke Tests'
            }
        }
    }
}