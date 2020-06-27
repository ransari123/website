CODE_CHANGES = 'None'
pipeline {
  agent any
    stages {
      stage("build") {
        steps {
           echo "Building the application"
           sh /var/lib/jenkins/workspace/my-app_master/build.sh
        }
      }
      stage("test") {
        when {
          expression {
             BRANCH_NAME == 'master' && CODE_CHANGES == 'None'
          }
        }
        steps {
          echo "Testing the application"
        }
      }
      stage("deploy") {
        steps {
          echo "deplyoying the application"
        }
      }
   }
  post {
     always {
         echo "Send an email"
     }
     success {
         echo "Build successful"
     }
     failure {
        echo "Build failure"
     }
  }
}
         
           
