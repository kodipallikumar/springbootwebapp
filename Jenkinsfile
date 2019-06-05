pipeline {
    agent any
    stages {
        stage('clean') {
            steps {
                echo "Maven Clean Started"
                bat 'mvn -B clean verify'
                echo "Maven Clean Completed"
            }
        }
stage ('test'){
steps{
    echo "Maven Test Started"
    bat 'mvn -B test verify'
    echo "Maven test Completed"
    }
  }
        stage ('build'){
        steps{
            echo "Maven package Started"
                bat 'mvn -B package verify'
           echo "Maven package Completed"
            
            }

 }
         stage ('deploy'){
        steps{
            echo "Maven deploy Started"
                bat 'copy target\\*.jar C:\\Installables\\Tomcat8\\apache-tomcat-8.5.41\\webapps\\'
           echo "Maven deploy Completed"
              }
 }
   
}
   -- post {
     --   always {
      --      mail bcc: '', body: 'This is a test email for notification', cc: '', from: '', replyTo: '', subject: 'jenkinsPipeline Status', to: 'kodipalli@gmail.com'
      --  }
   -- }
}

