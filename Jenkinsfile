pipeline {
   environment {
        registry = "swe645docker/swe645-group-project"
        registryCredential = 'dockerID'
    }
   agent any

   stages {
      stage('Build') {
         steps {
            script{
               sh 'rm -rf *.war'
               sh 'jar -cvf studentSurveyForm.war -C src/main/webapp/ .'
               //sh 'echo ${BUILD_TIMESTAMP}'

               docker.withRegistry('',registryCredential){
            def customImage = docker.build("averma24/studentsurveyassignment:0.1")
               }
            }
         }
      }

      stage('Push Image to Dockerhub') {
         steps {
            script{
               docker.withRegistry('',registryCredential){
                  sh 'docker push averma24/studentsurveyassignment:0.1'
               }
            }
         }
      }

      stage('Deploying Rancher to single pod') {
         steps {
            script{
               sh 'kubectl set image deployment/deploymentone container-0=averma24/studentsurveyassignment:0.1'
            }
         }
      }

      stage('Deploying Rancher as with load balancer') {
         steps {
            script{
               sh 'kubectl set image deployment/deploymentone-lb container-0=averma24/studentsurveyassignment:0.1'
            }
         }
      }
   }
}