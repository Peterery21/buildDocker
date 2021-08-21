node{
    def app
    stage('clone'){
        checkout scm
    }
    stage('build image'){
        app = docker.build('peter/nginx')
    }
    stage('test image'){
        docker.image("peter/nginx").withRun('-p 80:80'){ c ->
            sh 'docker ps'
            sh 'curl localhost'
        }
    }
}
