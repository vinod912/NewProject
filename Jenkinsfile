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
              stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8.5(credentialsId: 'tomcat_credential', path: '', url: 'http://localhost:8090')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' 
        }
      }
    }
                   }
                 }
