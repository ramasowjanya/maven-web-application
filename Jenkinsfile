node{
    
    echo "Job name is: ${env.JOB_NAME}"
echo "Build number is: ${env.BUILD_NUMBER}"
echo "Node name is: ${env.NODE_NAME}"
echo "Jenkins Home dir is: ${env.JENKINS_HOME}"

    
def mavenHome = tool name: 'maven3.9.8'    

stage('CheckoutCode'){
git branch: 'development', credentialsId: '5a7d3f67-cabf-45fb-9f68-335ece9085b4', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}

stage('UploadArtifcaysIntoNexus'){
sh "${mavenHome}/bin/mvn clean deploy"
}

stage('DeployAppInTomcatServer'){
sshagent(['8b9a05a7-5c2c-4f39-b63d-15178827b5d6']) {
 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.7.83:/opt/apache-tomcat-9.0.98/webapps/"   
}
}
*/
  
}
