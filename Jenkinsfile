pipeline{
  agent any

  stages{
    stage("pull the latest code"){
      steps{
        echo "the latest code has been pulled"
      }
    }
    stage("run hello message"){
      steps{
        sh "python3 hello.py"
      }
    }   
}
}
