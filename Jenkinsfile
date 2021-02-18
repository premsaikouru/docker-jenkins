node {
    def app
    stage('clone repository') {

        checkout scm
    }
    stage('Build image") {
        
	app=docker.build("premsaikouru/docker-jenkins")
    }
    
    stage('test') {
 	app.inside {
	    sh 'echo  "Test passed" '

	}
    }
    stage('push image') {

	  docker.withRegistry('https://regitry.hub.docker.com', 'docker-hub-credentials'

	     app.push("${env.BUILD_NUMBER}")
             app.push("latest")
    }
}
