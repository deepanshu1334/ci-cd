// pipeline {
//   agent any
//   stages {
//     stage('Build') {
//       steps {
//         sh 'docker-compose build'
//       }
//     }
//     stage('Test') {
//       steps {
//         sh 'npm test'
//       }
//     }
//     stage('Deploy') {
//       steps {
//         sh 'docker-compose up -d'
//       }
//     }
//   }
// }




// pipeline {
//   agent any
//   stages {
//     stage('Build') {
//       steps {
//         sh 'docker-compose build'
//       }
//     }
//     stage('Test') {
//       steps {
//         script {
//           docker.image('node:16').inside {
//             sh 'npm install'
//             sh 'npm test'
//           }
//         }
//       }
//     }
//     stage('Deploy') {
//       steps {
//         sh 'docker-compose up -d'
//       }
//     }
//   }
// }



// pipeline {
//   agent any
//   stages {
//     stage('Build') {
//       steps {
//         sh 'docker-compose build'
//       }
//     }
//     stage('Test') {
//       steps {
//         script {
//           docker.image('node:16').inside {
//             sh 'npm install'
//             sh 'npm test'
//           }
//         }
//       }
//     }
//     stage('Deploy') {
//       steps {
//         sh 'docker-compose up -d'
//       }
//     }
//     stage('Deploy to Kubernetes') {
//       steps {
//         sh 'kubectl apply -f k8s-deployment.yml'
//       }
//     }
//   }
// }






// pipeline {
//   agent any
//   stages {
//     stage('Build') {
//       steps {
//         sh 'docker-compose build'
//       }
//     }
//     stage('Test') {
//       steps {
//         script {
//           docker.image('node:16').inside {
//             sh 'npm install'
//             sh 'npm test'
//           }
//         }
//       }
//     }
//     stage('Deploy') {
//       steps {
//         sh 'docker-compose up -d'
//       }
//     }
//     stage('Deploy to Kubernetes') {
//       steps {
//         script {
//           docker.image('bitnami/kubectl').inside {
//             sh 'kubectl apply -f k8s-deployment.yml'
//           }
//         }
//       }
//     }
//   }
// }




pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker-compose build'
      }
    }
    stage('Test') {
      steps {
        script {
          docker.image('node:16').inside {
            sh 'npm install'
            sh 'npm test'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'docker-compose up -d'
      }
    }
    stage('List Files') {
    steps {
        sh 'ls -R /var/jenkins_home/workspace/ci-cd'
     }
    }

    stage('Deploy to Kubernetes') {
      steps {
            sh 'kubectl apply -f k8s-deployment.yml'        
      }
    }
  }
}





























































































