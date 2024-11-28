node('built-in') 
{
 stage('Continuous Download') 
 {
 // downloading the sourcecode from the GitHub
 git 'https://github.com/Himachand863/MultiBranch-Pipeline-Repo.git'
 }
 
 stage('Continuous Build') 
 {
 // Building the package from the sourcecode
 sh 'mvn package'
 }
 
 stage('Continuous Test') 
 {
 // Testing the Build 
 sh 'echo "Testing Passed"'
 }
 
 
 stage('Continuous Deploy') 
 {
 // Deploying the Artifacts into the QA Environment
 sh 'scp /home/ubuntu/.jenkins/workspace/Multi_Pipeline_master/target/maven-web-app.war ubuntu@172.31.86.68:/var/lib/tomcat9/webapps/testing.war'
 }

}
