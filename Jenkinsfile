
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
      stage('SCM') {
    git credentialsId: 'GithubRepo', url: 'https://github.com/supratim230184/JavaSonar.git'
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Maven1';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=javasonar"
    }
  }
    }
  
  
}
