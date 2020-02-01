node("linux") {
def customImage = ""
stage('Clone sources') {
        git url: 'https://github.com/IdoBaram/flask-http.git'
}
stage("build docker") {
customImage = 
docker.build("idobaram/mid-course-app")
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