pipeline {
agent any
  		stages {
        			
        	stage('Clone sources') 
{
 			steps 
{
git url: 'https://github.com/mohankrishna1990/spring-boot-swagger.git'
}
}
        			stage('SonarQube analysis')
 {
            			steps 
{
withSonarQubeEnv('SonarQube')
 {
def mavenImage = docker.image('openjdk:11')
mavenImage.inside() 
{
sh "mvn clean verify sonar:sonar -Dsonar.projectKey=Springboot-hello"
}
}
}
}
stage("Quality gate") 
{
steps 
{
 waitForQualityGate abortPipeline: true
}
}
}
}
