pipeline {
     agent any
     stages {
         stage('Clean Workspace') {
             steps {
                  deleteDir()                  
             }
         }
         stage('Clone Project') {
             steps {                  
                  checkout scm                  
             }
         }
         stage ('JDK_11') {
             tools {
            jdk 'java'
            }
             steps{
               sh '''
              java -version
              '''
            }
        }
       stage ('Build') {    
            tools {
                nodejs 'Nodejs'
             }

         steps {
           echo "Starting Build"
           sh 'npm install -g @angular/cli@6.0.8'
           sh 'npm install @angular-devkit/core --save-dev'
           sh 'ng build'
         }
       }
     }
 }
