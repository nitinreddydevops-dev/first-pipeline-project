pipeline{
  agent any

  stages{
    stage("pull the latest code"){
      steps{
        echo "the latest code has been pulled"
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
    stage("run hello message"){
      steps{
        sh "python3 hello.py"
      }
    }   
}
}
