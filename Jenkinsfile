pipeline{
agent any
	stages{
		stage('SCM Checkout_Master'){
			steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/abhinavthula/sampleproject.git']]])
            }
		}
		stage('Continuos Build_Master'){
			steps{
				 sh 'mvn package'
			}
		}
		//stage('Continuous Testing_Master') {
              //sh label: '', script: 'echo "Testing Passed"'
		//}
		//stage('Continuous Delivery_Master'){
		  //  steps {
		    //    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war   ubuntu@172.31.44.115:/var/lib/tomcat8/webapps/qaenv.war'
		    //}
		//}
	}
}
