pipeline {
     agent {
          label 'windows_client'
     }
         stages {
                stage('---Clean---') {
                      steps {
                          
                        bat "mvn clean"
                           }
                       }
                 stage('--Test--'){
                        steps{
                         bat "mvn test"
                      }
                
                   }
               stage('--Package--'){
                           steps{
                            bat "mvn package"
                                }
                              }
                   }
                 }
