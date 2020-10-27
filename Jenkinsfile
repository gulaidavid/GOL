pipeline{
agent any
  stages {
    stage('Compile') {
      steps {
        sh 'mvn compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
      post {
      always {
        junit 'gameoflife-web/target/surefire-reports/*.xml'
      }
      }
    }
    stage('Package') {
    agent any
      steps {
      sh 'mvn package'
      }
    }
  }

}
