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
          deploy adapters: [tomcat8(credentialsId: '8929a8ad-ee8b-4a21-a899-f4f570b16f14', path: '', url: 'http://localhost:8090')], contextPath: '/pipeline', onFailure: false, jar: 'WEB-INF/lib/*.jar' 
        }
      }
    }
                   }
                 }
