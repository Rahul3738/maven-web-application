// By default script is going to run on matser instance.
// If you want to specify specify like below syntax.

node{
    
    echo "The Job name is: ${env.JOB_NAME}"
    echo "The Nod ename is: ${env.NODE_NAME}"
    echo "The Build Number is: ${env.BUILD_NUMBER}"
    echo "The Jenkins Home directory is: ${JENKINS_HOME}"

//def is keyword to declare variable mavenhome is keyword
    def mavenhome = tool name: "maven3.8.5"

    //CheckoutCode you can use any name 
    stage('CheckoutCode'){
        git branch: 'development', credentialsId: 'GitHub_Credentials', url: 'https://github.com/Rahul3738/maven-web-application.git'
    }

    stage('Build'){
        sh "$mavenhome/bin/mvn clean package"
    }

    //stage('Build'){
    //    sh "mvn clean package"
    //}
/*
    stage('SonarQubeReport'){
        sh "$mavenhome/bin/mvn sonar:sonar"
    }

    stage('UploadArtifactsIntoNexus'){
        sh "$mavenhome/bin/mvn deploy"
    }
    
    ///Deploy App to Tomcat Stage
    stage('DeployWarToTomcat'){
        sshagent(['15a6d91a-850c-4142-8387-dfc4867c551c']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.110.43.184:/opt/tomcat/webapps"
    }
    }
    
*/    
}
