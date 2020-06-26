node{
   stage ('SCM Checkout') {
    git 'https://github.com/praveenaws1983/my-app'
   }
   stage ('Compile-Package'){
    def mvnHome = tool name: 'maven-3', type: 'maven'
      sh "${mvnHome}/bin/mvn package"
   }
   stage ('Email Notification'){
      mail bcc: '', body: '''welcome to jenkins job mailing
      '', cc: '', from: '', replyTo: '', subject: 'jenkins job', to: 'praveenaws1983@gmail.com'  
   }
}
