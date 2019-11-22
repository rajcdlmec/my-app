  node{
   stage('SCM Checkout'){
     git 'https://github.com/rajcdlmec/my-app'
   }
   stage('Compile-Package'){
    
      def mvnHome =  tool name: 'maven-3', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
    stage('Email Notification'){
       mail bcc: '', body: '''Welcome to Jenkins Email Alerts
       Thanks
       Rajesh''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'rajesh.kumar@wemonde.com'
    }
    
    stage('Slack Notification'){
       slackSend baseUrl: 'https://hooks.slack.com/services/', 
         channel: '#jenkins-pipeline-demo', 
         color: 'good', 
         message: 'Welcome to Jenkins, Slack!', 
         teamDomain: 'wemonde', 
         tokenCredentialId: 'slack-demo'
    }
}


