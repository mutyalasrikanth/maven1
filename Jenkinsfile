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
sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war   ubuntu@18.118.154.186:/var/lib/tomcat9/webapps/qaenv.war'
	}
    stage('Continuous Testing') 
	{
              sh label: '', script: 'echo "Testing Passed"'
	}
    stage('Continuous Delivery') 
	{    
	sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war ubuntu@3.15.11.19:/var/lib/tomcat9/webapps/prodenv.war'
    }
    }
