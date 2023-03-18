pipeline {
  environment {
    dockerimagename = "nilapp20/nodeapp"
    dockerImage = ""
  
  }
  
  agent any

  stages {

//     stage('Checkout Source') {
//       steps {
//         git 'https://github.com/SwapnilDA-20/kubernetes_Jenkins_deployment.git'
//       }
//     }
        
    stage('Build Container') {
      steps {
        echo 'Building Container..'
                script {
                    def dockerHome = tool 'MyDocker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                }
      }
    }

    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build dockerimagename
        }
      }
    }
      
          stage('Build B') {
             steps {
                 build job: "Sonar_Project", wait: true
                    }
                }
    
    //     stage('Pushing Image') {
//          environment {
//                registryCredential = 'dockerhubcred'
//            }
//       steps{
//         script {
//           docker.withRegistry( 'https://registry.hub.docker.com', registryCredential ) {
//           dockerImage.push("${env.BUILD_NUMBER}")            
//           dockerImage.push("latest")        
//           }
//         }
//       }
//     }
    
 //   stage('SonarQube analysis') {
 //   steps {
 //       withSonarQubeEnv('SonarQube Server') {
 //           sh 'docker run --rm -e SONAR_HOST_URL=http://34.201.241.166:9000 -e SONAR_LOGIN=MNYHILdg7TqhC7T8Kil/DJTY7AV2fSukvuvzMXwotZ8= -v $(pwd):/usr/src -w /usr/src dockerimagename sonar-scanner'
 //       }
 //   }
// }




//     stage('Deploying App to Kubernetes') {
//       steps {
//         script {
//           kubernetesDeploy(configs: "deploymentservice.yml", kubeconfigId: "kubernetes")
//         }
//       }
//     }

  }

}
