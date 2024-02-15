pipeline{
  agent { label 'test'}
  tools{
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
    stage("Clean Workspace"){
      steps{
         cleanWs()
      }
    }
    stage("Checkout From SCM"){
        steps{
          git branch: 'main', credentialsId: 'github', url: 'https://github.com/jaatbreak/register-app'
        }
    }
    stage("Build Application"){
      steps{
        sh "mvn clean package"
      }
    }
    stage("Test Application"){
      steps{
        sh "mvn test"
      }
    }
    
  }
}
