//Jenkins pipeline scripty
//Groovy script 

node{
  def mavenHome = tool name: 'Maven3.8.1'
  
  stage('CodeClone') {
    git credentialsId: 'gitcre', url: 'https://github.com/Oriyomi-Johnson/maven-web-apps'
  }
    stage('mavenBuild') {
    sh "${mavenHome}/bin/mvn clean package"
  }
/*
  stage('CodeQuality') {
    sh "${mavenHome}/bin/mvn sonar:sonar"
  // execute the CodeQuality report with sonar
  }
  stage('emailQualityIssues') {
    emailext body: '''Thanks

Landmark Technologies''', recipientProviders: [developers()], subject: 'status of build', to: 'mylandmarktech@gmail.com'
  }

   stage('UploadNexus') {
    sh "${mavenHome}/bin/mvn deploy"
    //mvn deploy  are uploaded in to nexus
  }
*/
   {
    deploy adapters: [tomcat9(credentialsId: 'Tom', path: '', url: 'http://3.17.152.65:8080/')], contextPath: null, war: 'target/*war'
  }
  /*
  stage('emailDeployIssues') {
    emailext body: '''Thanks

Landmark Technologies''', recipientProviders: [developers()], subject: 'status of build', to: 'mylandmarktech@gmail.com'
  }
 */ 
}
