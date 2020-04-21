pipeline {
    agent any
    stages {
      stage('Build') {
        steps {
          sh 'echo "Hello World"'
          sh '''
            echo " Multiline shell shell works too "
          '''
          }
        }
      stage('Upload to AWS')
        {
          withAWS(roleAccount: '705889244582', principalArn: 'arn:aws:s3:::jenkins-prannay-project', samlAssertion: 'base64SAML', region:'us-east-1') 
          {
            s3Upload(file:'index.html', bucket:'jenkins-prannay-project', path:'path/to/target/index.html')
          }
        }
      }
    }
}   
      
