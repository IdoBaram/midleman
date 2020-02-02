node("linux") {
def customImage = ""
stage('Clone sources') {
        git url: 'https://github.com/IdoBaram/jenkins-docker.git'
}
stage("build docker") {
customImage = 
docker.build("idobaram/mid-course-cicd")
}
stage("verify dockers") {
sh "docker images"
}
stage("register image") {
withDockerRegistry(credentialsId: 'dockerhub.idobaram', url: '') {
    customImage.push()
}
}
}
