node {
   def mvnHome
   stage('getscm') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/sivakumar46/spring3-mvc-maven-xml-hello-world.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.
      mvnHome = tool 'Maven'
   }
   stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
      echo 'this is build maven artifact'
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('artifact')
   {
   archive 'target/*.war'
   }
   stage ('deploy'){
   echo 'deployment started'
       bat '''copy C:\\Users\\Administrator\\.jenkins\\workspace\\pipelinesyntax\\target\\*.war C:\\Users\\Administrator\\Documents\\apache-tomcat-7.0.99\\webapps\\'''
   }

}
