pipeline {
  agent any
     stages {
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
                        sh './jen-shell.sh'
                      }
                  }  
              }
          }     
     }
}      
