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
        stage ('Compile Test') {

            steps {
                withMaven(maven : 'mvn_home') {
                    sh 'mvn test'
                }
            }
}
}
}
