pipeline{
  agent any
  environment{
    APP_NAME = "jenkins-pipeline-app-example"
    OWNER = "Nitn Reddy"
    DOCKERHUB = credentials("dockerhub_creds")
    
  }

  stages{
    stage("pull the latest code"){
      steps{
        echo "the latest code has been pulled"
      }
    }
    stage("login to docker hub"){
      steps{
        sh 'docker login -u $DOCKERHUB_USR  -p $DOCKERHUB_PSW '
      }
    }
    stage("just echoing build number, job name, workspace, got commit message"){
      steps{
        sh "echo buildnumber is ${BUILD_NUMBER}"
        sh "echo workspace is ${WORKSPACE}"
        sh "echo job name is ${JOB_NAME}"
        sh "echo git commit is ${GIT_COMMIT}"   
      }
    }
     stage("show custom env"){
       steps{
         sh "echo app name is ${APP_NAME}, built by ${OWNER}"
      } 
    }
    stage('build the image'){
      steps{
        sh 'docker build -t nitinreddy8/$APP_NAME:$BUILD_NUMBER .'
      }
    }
    stage('pushed built image to dockerhub'){
      steps{
        sh 'docker push nitinreddy8/$APP_NAME:BUILD_NUMBER'
      }
    }
}
}
