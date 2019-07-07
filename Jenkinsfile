 pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/prakashk0301/maven-project'
        }
  }
    {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'mvn_home') {
                    sh 'mvn clean compile'
                }
            }
}
        stage (' Test Stage') {

            steps {
                withMaven(maven : 'mvn_home') {
                    sh 'mvn test'
                }
            }
        }
         stage (' package Stage') {

            steps {
                withMaven(maven : 'mvn_home') {
                    sh 'mvn package'
                }
            }
          }
         stage (' install Stage') {

            steps {
                withMaven(maven : 'mvn_home') {
                    sh 'mvn clean install'
                }
            }
          }
         stage (' Deploy Stage') {

            steps {
                withMaven(maven : 'mvn_home') {
                    sh 'mvn deploy'
                }
            }
}
}
}
