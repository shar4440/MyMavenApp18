pipeline{
  agent any

  tools{
    maven 'Maven'
  }

  stages{
    stage('checkout'){
      steps{
        git branch: 'master' , url: 'https://github.com/shar4440/MyMavenApp18.git'
      }
    }

    stage('build'){
      steps{
        sh 'mvn clean package'
      }
    }

    stage('test'){
      steps{
        sh 'mvn test'
      }
    }

    stage('run'){
      steps{
        sh 'java -jar target/MyMavenApp18-1.0-SNAPSHOT.jar'
      }
    }
  }

  post{
    success{
      echo 'success in build and test'
    }

    failure{
      echo 'better luck next time'
    }
  }
}
