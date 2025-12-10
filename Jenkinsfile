@Library('Shared') _
pipeline {
    agent { label "vinod" }

    stages {

        stage("Hello") {
            steps {
                script {
                    hello()
                }
            }
        }

        stage("Code") {
            steps {
                script {
                    clone("https://github.com/shivam0786tab/django-notes-app.git", "main")
                }
            }
        }

        stage("Build") {
            steps {
                script {
                    build("shiv0786", "test-repo", "latest")
                }
            }
        }

        stage("Test") {
            steps {
                echo "This is testing the code"
            }
        }

        stage("Push Image") {
            steps {
                script {
                    deploy("test-repo", "latest")
                }
            }
        }

        stage("Deploy") {
            steps {
                echo "This is deploying the code"
                sh "docker compose up -d"   // or docker-compose
            }
        }
    }
}
