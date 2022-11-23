pipeline {
  agent any; 
  parameters {
    string defaultValue: '12334', description: 'ngfvgjkhjlkvhf', name: 'sujay', trim: true 
    credentials credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: '', name: 'banking', required: false
  file ''
  choice choices: ['master slave', 'main1', 'main0'], name: 'branch'
  password defaultValue: '1234567', name: 'passcode'
  } 
  stages {
        stage ('BUILD') {
  steps {
            git(
                  'https://github.com/sujayprabhu/java-sample.git' 
                )   
         sh '''
            mvn clean package
            '''
         }
       }   
    stage ('TEST PARALLEL') {
      parallel {
        stage ('TEST ON CHROME') {
           steps {
             echo "this is test stage on chrome"
             sh "sleep 5"
           }
        }
         stage ('TEST on firefox') {
           steps {
             echo "this is test stage on firefox"
             sh "sleep 5"
           }
        }  
      } 
    }    
     
    stage ('DEPLOY') {
      steps {
        echo "this is deploy stage "
        sh "sleep 5"
      }
    }
  }
}
