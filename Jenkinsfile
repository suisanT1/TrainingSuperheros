pipeline {
  agent any
  stages {
    stage('build') {
       // when {
       //  expression {
       //    BRANCH_NAME == 'dev' && CODE_CHANGES == true
       //  }
      // }
      steps {
        echo "building the application"
      }
    }
    

    stage('test') {
      // when {
      //   expression {
      //     BRANCH_NAME == 'dev' || BRANCH_NAME == 'main'
      //   }
      // }
      steps {
         echo "testing the application"
        sh 'ls -all'
      }
    }
    stage('deploy') {
      steps {
         echo "deploying the application"
        sh 'ls -all'
      }
    }
  post {
    always {
      //
    }
    success {
      //
    }
    failure {
      //
    }
  }
  }
}
