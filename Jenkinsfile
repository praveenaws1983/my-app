properties([parameters([choice(choices: 'master\ndev\nsit\nuat', description: 'select the branch', name: 'branch')])])

node{
   stage ('SCM Checkout') {
      echo 'pulling the changes form ${params.branch}'
      git url: 'https://github.com/praveenaws1983/my-app', branch: '${params.branch}'
   }
   stage ('Compile-Package'){
    def mvnHome = tool name: 'maven-3', type: 'maven'
      sh "${mvnHome}/bin/mvn package"
   }
   stage ('deploy war to tomcat'){
      sshagent(['ec2-user']) {
         // some block
         sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.36.41:/opt/tomcat/webapps/'
      }
   }
}
