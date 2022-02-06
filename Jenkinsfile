node {
  stage('SCM') {
    git 'https://github.com/mohankrishna1990/java.git'
  }
  stage('SonarQube analysis') {
    withSonarQubeEnv(credentialsId: 'a209187b11fc59837532190b85616a5b8dbe2f96', installationName: 'ffg') { // You can override the credential to be used
      bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
    }
  }
}
