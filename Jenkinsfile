def gv

pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage("init") {
            steps {
                script {
                   gv = load "script.groovy" 
                }
                echo "init the application"
            }
        }
        stage("build") {
            steps {
                script {
                    gv.buildApp()
                }
                echo "build the application"
            }
        }
        stage("test") {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                script {
                    gv.testApp()
                }
                echo "test the application"
            }
        }
        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                }
                echo "deploy the application"
            }
        }
    }   
}

// pipeline {
//   agent any
//   // tools {

//   // }
//   // environment {
//   //   NEW_VERSION = '1.3.0'
//   //   SERVER_CREDENTIALS = credentials('server-user')
//   // }
//   parameters {
//     choice (name: "VERSION", choices: ['1.0.2', '1.0.3', '1.0.4'], description:'')
//     booleanParam(name: 'executeTest', defaultValue: true, description: '')
//   }

//   stages {
//     stage('build') {
//        // when {
//        //  expression {
//        //    BRANCH_NAME == 'dev' && CODE_CHANGES == true
//        //  }
//       // }

//       steps {
//         echo "building the application"
//         echo "building the application ${params.VERSION}"

//       }
//     }
    

//     stage('test') {
//       // when {
//       //   expression {
//       //     BRANCH_NAME == 'dev' || BRANCH_NAME == 'main'
//       //   }
//       // }
//       when {
//         expression {
//           params.executeTest
//         }
//       }
//       steps {
//         echo "testing the application"
//         sh 'ls -all'

//       }
//     }
//     stage('deploy') {
//       steps {
//         echo "deploying the application"
//         sh 'ls -all'
//         echo "deploying with ${SERVER_CREDENTIALS}"
//         // withCredentials([
//         //   usernamePassword(credentials:'server-user', usernamevariable: USER, passwordVariable: USER)
//         // ]) {
//         //   sh "some script ${USER} ${PWD}"
//         // }
//       }
//     }
//   post {
//     always {
//       //
//     }
//     success {
//       //
//     }
//     failure {
//       //
//     }
//   }
//   }
// }

