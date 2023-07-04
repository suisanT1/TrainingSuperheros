pipeline {
  agent any
  // tools {

  // }
  // environment {
  //   NEW_VERSION = '1.3.0'
  //   SERVER_CREDENTIALS = credentials('server-user')
  // }
  parameters {
    choice (name: "VERSION", choices: ['1.0.2', '1.0.3', '1.0.4'], description:'')
    booleanParam(name: 'executeTest', defaultValue: true, description: '')
  }

  stages {
    stage('build') {
       // when {
       //  expression {
       //    BRANCH_NAME == 'dev' && CODE_CHANGES == true
       //  }
      // }

      steps {
        echo "building the application"
        echo "building the application ${params.VERSION}"

      }
    }
    

    stage('test') {
      // when {
      //   expression {
      //     BRANCH_NAME == 'dev' || BRANCH_NAME == 'main'
      //   }
      // }
      when {
        expression {
          params.executeTest
        }
      }
      steps {
        echo "testing the application"
        sh 'ls -all'

      }
    }
    stage('deploy') {
      steps {
        echo "deploying the application"
        sh 'ls -all'
        echo "deploying with ${SERVER_CREDENTIALS}"
        // withCredentials([
        //   usernamePassword(credentials:'server-user', usernamevariable: USER, passwordVariable: USER)
        // ]) {
        //   sh "some script ${USER} ${PWD}"
        // }
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
