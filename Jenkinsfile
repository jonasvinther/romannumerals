node {
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git credentialsId: 'ae36df52-130d-48e1-bbea-53a830c8185f', url: 'git@github.com:jonasvinther/romannumerals.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      
   }
   stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "mvn -Dmaven.test.failure.ignore clean package"
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
