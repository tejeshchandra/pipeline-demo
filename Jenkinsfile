node ("Slave1"){
   def mvnHome
   stage('Preparation') { 
      
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                
      mvnHome = tool 'M3'
   }
   stage('Build') {
      
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
