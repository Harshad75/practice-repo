pipeline {
  agent {
    node {
      label 'build'
    }
  }

environment {
  PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
}

  stages {
    stage("Build the Source Code") {
      steps {
        sh 'mvn clean deploy -Dmaven.test.skip=true'
      }
    }
    stage("Unit Test") {
      steps {
        sh 'mvn surefire-report:report'
      }
    }
 }
}

