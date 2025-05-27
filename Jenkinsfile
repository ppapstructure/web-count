node {
    
    stage('Clone repository') {
        git(
          url: 'https://github.com/ppapstructure/web-count.git',
          credentialsId: 'github_access_token'
        )
    }

    stage('Build image') {
       dockerImage = docker.build("noviceuser23/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
