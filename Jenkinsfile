pipeline{

agent any
  
  stages{

  stage('build-image'){
    steps{
      echo "Building Docker image"
      withCredentials([usernamepassword(CredentialsID:'docker',usernameVariable:'user',passwordVariable:'passwd')]){
      sh "docker build goutham2/24-7entertainment:entertainment-2.0 ."
        sh "docker login -u $user -p $passwd"
        sh "docker push goutham2/24-7entertainment:entertainment-2.0"
        
      }
    }
  }
  
  stage('test'){
  
    steps{echo "Iam at test stage";}
  }

  stage('deploy'){    steps{echo "Iam at deploy stage";} }
  }
}
