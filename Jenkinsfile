pipeline {

    agent any

    stages {

        stage("Building docker image") {

            steps {

                echo "Building docker image ..."
                sh 'docker build ./api/'
                sh 'docker build ./web/'

            }

        }

         stage("Push docker image") {

            steps {

                echo "Pushing docker image ..."

            }

        }

        stage("Clean docker image") {

            steps {

                echo "Cleaning docker image ..."
            }

        }

    }

}