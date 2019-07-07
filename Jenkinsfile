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
                sshagent (credentials: ['a42942cf-8457-4e1e-9331-14499717b85a']) {
                  sh 'scp -o StrictHostKeyChecking=no **/*.war  ec2-user@172.31.20.99:/usr/share/tomcat/webapp/'
                }
            }
}
}
}
