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
		  sh 'mvn sonar:sonar -Dsonar.host.url=http://13.60.31.108:9000 -Dsonar.login=6d90a7cb3fe5201218eba44324531469bdbc8f32'
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



