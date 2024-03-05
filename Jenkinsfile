pipeline {
    agent any

    tools {
       maven 'maven-3.9.6'
    }

    stages {
        stage('git clone') {
            steps {
              git credentialsId: 'github', url: 'https://github.com/vijayakumarpadavala/ks.git'
            }
        }
		stage('Maven version')
		{
		  steps {
		  sh 'mvn --version'
		  }
		}
		stage('Maven Clean')
		{
		  steps {
		  sh 'mvn clean'
		  }
		}
		stage('Maven validate')
		{
		  steps {
		  sh 'mvn validate'
		  }
		}
		stage('sonar scan')
		{
		  steps {
		  sh 'mvn sonar:sonar -Dsonar.host.url=http://16.171.194.165:9000 -Dsonar.login=4ddfdaa940d68aa074df55464851d42fb19b609e'
		  }
		}
		
		stage('Maven compile')
		{
		  steps {
		  sh 'mvn compile'
		  }
		}
		stage('Maven Test')
		{
		  steps {
		  sh 'mvn test'
		  }
		}				
		stage('Maven Package')
		{
		  steps {
		  sh 'mvn package'
		  }
		}
		stage('Maven Deploy')
		{
		  steps {
		  sh 'mvn deploy'
		  }
		}
	}
}



