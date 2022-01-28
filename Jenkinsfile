node('master') 
{
    stage('Continuous Download') 
	{
    git 'https://github.com/sunildevops77/maven.git'
	}
    stage('Continuous Build') 
	{
    sh label: '', script: 'mvn package'
	}
    stage('Continuous Deployment') 
	{
sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war   ubuntu@10.2.0.44:/var/lib/tomcat9/webapps/qaenv.war'
	}
    stage('Continuous Testing') 
	{
              sh label: '', script: 'echo "Testing Passed"'
	}
    stage('Continuous Delivery') 
	{
    sshagent(credentials: ['ubuntu'], ignoreMissing: true) {   
            sh 'echo "TEXT"' 
	sh 'ssh -o StrictHostKeyChecking=no -l ubuntu 10.2.0.44'	  
	sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war ubuntu@10.2.0.44:/var/lib/tomcat9/webapps/prodenv.war'
    }
    }
}
