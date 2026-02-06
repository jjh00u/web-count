node {
    stage('Clone repository') {
        git branch: 'main',
        git credentialsId: 'github-access-token', url: 'https://github.com/jjh00u/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("jjhoou/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
