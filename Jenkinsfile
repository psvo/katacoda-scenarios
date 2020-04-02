node {
    stage('Preparation') { // for display purposes
        deleteDir()
        // Get some code from a GitHub repository
        git 'https://github.com/jglick/simple-maven-project-with-tests.git'
    }
    docker.image('maven:3-jdk-11').inside('-e NAME=value') {
      stage('Build') {
        sh 'echo "--$NAME--"'
        sh 'mvn -Dmaven.test.failure.ignore clean package'
      }
      stage('Results') {
         junit '**/target/surefire-reports/TEST-*.xml'
         archiveArtifacts 'target/*.jar'
      }
   }
}
