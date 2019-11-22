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
}


