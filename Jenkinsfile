node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   git url: 'git@github.com:TTFHW/jenkins_pipeline_shell_scripts.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'apache-maven-3.5.0'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean package"
   step([$class: 'JUnitResultArchiver', testResults: '*/master'])
}
