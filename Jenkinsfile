pipeline {
    agent any
	tools {
	  maven 'Maven'

    stages {
		
        stage ('Build Stage') {

            steps {
			dir("/var/lib/jenkins/workspace/Sukku"){
			def mvn_version = 'M3'
			withEnv( ["PATH+MAVEN=${/opt/maven}/bin"] ) {
			sh 'mvn clean install'
			}
            }
            }
        }

        
		stage ('Deployment Stage') {

            steps {
                
                    sh 'cp /var/lib/jenkins/workspace/Sukku/target/simple-web-app.war /opt/apache-tomcat-8.5.34/webapps '
              
            }
        }


        
    }
}
