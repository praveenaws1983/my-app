node{
   stage ('SCM Checkout') {
    git 'https://github.com/praveenaws1983/my-app'
   }
   stage ('Compile-Package'){
    def mvnHome = tool name: 'maven-3', type: 'maven'
      sh '${mvnHome}/bin/mvn package'
   }
}
