node
{
 
  stage("CheckOutCodeGit")
  {
   git branch: 'main', url: 'https://github.com/edublessed22/devops-code-challenge'
 }
 
 stage("Build")
 {
 nodejs(nodeJSInstallationName: 'nodejs8.10.0') {
        sh 'npm install'
    }
 }  
 
  stage('ExecuteSonarQubeReport') {
     nodejs(nodeJSInstallationName: 'nodejs8.10.0') {
        sh 'npm run sonar'
    }
      
        } 
		
    stage('UploadintoNexus') {
       nodejs(nodeJSInstallationName: 'nodejs8.10.0') {
          sh 'npm publish'
      }
      
          }	
 
 stage('RunNodeJsApp')
 {
 //sh "./scripts/run.sh"
 nodejs(nodeJSInstallationName: 'nodejs8.10.0') {
        sh 'npm start &'
    }
}    
    
}
