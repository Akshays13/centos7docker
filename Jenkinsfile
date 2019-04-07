node {
   stage('Preparation') {
      git changelog: false, credentialsId: '7e910930-ce99-4793-a885-e12b7329bc08', poll: false, url: 'https://github.com/Akshays13/centos7docker.git'
   }
   
   stage('docker') {
      
         sh script: 'docker build -t akshays13/sample2.v$BUILD_ID .'

      } 
      stage('docker_push') {
      
        withCredentials([usernamePassword(credentialsId: '12b5d327-cb08-4b87-8e45-5c87a0a3372d', passwordVariable: 'dockerpassword', usernameVariable: 'dockeruser')]) {
     sh script: 'docker login -u $dockeruser -p $dockerpassword'    
        }

    sh 'docker push akshays13/sample2.v$BUILD_ID'
        }
        
}
