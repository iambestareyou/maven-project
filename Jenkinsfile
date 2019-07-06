 pipeline {
     agent any
     stages {
       stage('Clone my SCM'){
         git 'https://github.com/iambestareyou/maven-project'
         }
       stage('Compile'){
       
         steps {
           withMaven(maven : 'mvn_home') {
             sh 'mvn compile'
             
             }
             }
             }
             }
             }
