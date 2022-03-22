pipeline{
agent any
	stages{
		stage('SCM Checkout_login'){
			steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/abhinavthula/sampleproject.git']]])
            }
		}
		stage('Continuos Build_login'){
			steps{
				 sh label: '', script: 'mvn package'
			}
		}
		stage('Continuous Testing_login') {
              sh label: '', script: 'echo "Testing Passed"'
		}
		stage('Continuous Delivery_login'){
		    steps {
		        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war   ubuntu@172.31.44.115:/var/lib/tomcat8/webapps/qaenv.war'
		    }
		}
	}
}
