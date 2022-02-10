pipeline {
agent any
  		stages {
        	stage('Clone sources') {
              steps {
                     git branch: 'main',
                     credentialsId: 'Github-username-password',
                     url: 'https://github.com/mohankrishna1990/java.git'
                  }
                }
        	stage('SonarQube'){
            	steps {
                    script{
                        withSonarQubeEnv('SonarQube analysis'){
                            //def mavenImage = docker.image('openjdk:11')
                            //mavenImage.inside() 
                            //{
                                bat "mvn clean verify sonar:sonar" -Dsonar.projectKey=Java" -Dsonar.host.url=http://localhost:9000" -Dsonar.login=455cc11ed1ffab8979265ddf36ea31d35e395139"
                            }
                        }
                   // }
                    }
                  }
                }
            }
