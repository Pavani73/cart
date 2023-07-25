pipeline {
  agent {
     node { label 'workstation' }
    }

   stages {

      stage('code Checkout') {
        steps {
          echo 'code checkout'
           }
      }

     stage('BUILD') {
        steps {
           sh 'npm install'
            }
      }

    stage('UNIT TESTS') {
        steps {
           echo 'UNIT TEST'
           //sh 'npm test'
            }
        }

    stage('CODE ANALYSIS') {
        steps {
          echo 'sonar'
          //sh 'sonar-scanner -Dsonar.host.url=http://172.31.86.8:9000 -Dsonar.login=admin -Dsonar.password=admin321 -Dsonar.projectKey=cart'
           }
        }

    stage('SECURITY SCAN') {
       steps {
          echo 'SECURITY SCAN'
          }
       }
    stage('PUBLISH A ARTIFACT WITH VERSION') {

    when{
       expression {
          env.TAG_NAME ==~ ".*"
          }
        }
       steps {
          echo 'PUBLISH A ARTIFACT WITH VERSION'
          }
      }

   }

}


