pipeline {
    environment {
        MY_KUBECONFIG = credentials('IDCONTTT')
    }
    agent any
    stages {

        stage("Building docker image") {

            steps {

                echo "Building docker image ..."
                sh 'docker build ./api/ -t jenkinscontainer1.azurecr.io/api-img:1.0'
                sh 'docker build ./web/ -t jenkinscontainer1.azurecr.io/web-img:1.0'

                sh 'docker images'

            }

        }

         stage("Push docker image") {

            steps {

                echo "Pushing docker image ..."
                sh 'docker login jenkinscontainer1'
                sh 'docker push jenkinscontainer1.azurecr.io/api-img:1.0'
                sh 'docker push jenkinscontainer1.azurecr.io/web-img:1.0'
            }

        }

        stage("Clean docker image") {

            steps {

                echo "Cleaning docker image ..."
            }

        }

    }

}