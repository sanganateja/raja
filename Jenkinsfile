pipeline {
  agent any
     stages {
       stage('chechout scm') {
         steps {
           git credentialsId: 'ravgit', url: 'https://github.com/sanganateja/raja.git'
           }
       }
       stage ('build') {
           steps {
               echo 'building'
            }
         }     
          stage ('test') {
            steps {
              echo 'testing'
            }
        }
          stage('Deploy') {
            steps {
                timeout(time: 3, unit: 'MINUTES') {
                    retry(5) {
                        sh './shell.sh'
                      }
                  }  
              }
          }     
     }
}      
