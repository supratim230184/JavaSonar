
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
      stage('SCM') {
           steps {
          git credentialsId: 'GithubRepo', url: 'https://github.com/supratim230184/JavaSonar.git'
           }
  }

stage('Package') {
            steps {
                bat 'mvn package'    
		            echo "Maven Package Goal Executed Successfully!";
            }
        }

        
     stage('SonarQube analysis') {
            steps {
		// Change this as per your Jenkins Configuration
                withSonarQubeEnv('sonar') {
                    bat 'mvn package sonar:sonar'
                }
            }
        }
    }
  
  
}
