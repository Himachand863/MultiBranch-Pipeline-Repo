node('built-in') 
{
  stage('Continuous Download') 
  {
    // Download the source code from GitHub
    git branch: "${env.BRANCH_NAME}", url: 'https://github.com/Himachand863/MultiBranch-Pipeline-Repo.git'
  }

  stage('Continuous Build') 
  {
    // Only build if the current branch is not master
    if (env.BRANCH_NAME != 'master') {
      // Building the package from the source code
      sh 'mvn package'
    } else {
      echo "Skipping build for master branch."
    }
  }
  
  stage('Continuous Test') 
  {
  // Testing the Build 
  sh 'echo "Testing Passed"'
  }
  
  stage('Deploy to Production') 
  {
            when {
                branch 'child'  // Replace with the name of your child branch
            }
            steps {
                // Deploy the application to the Production server
                script {
                    // Add production deployment logic, for example:
                    sh 'scp /home/ubuntu/.jenkins/workspace/MyPipeline/target/maven-web-app.war ubuntu@172.31.92.51:/var/lib/tomcat9/webapps/PROD.war'
                }
            }
        }
}
