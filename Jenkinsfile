pipeline {
  agent any; 
  parameters {
    string defaultValue: '12334', description: 'ngfvgjkhjlkvhf', name: 'sujay', trim: true
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
