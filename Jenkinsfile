node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }

    stage('Fetch') {
        checkout scm
    }

    stage('Docker Build') {
        sh 'docker build -t iaadefm/laravel:$BUILD_NUMBER .'
    }

    stage('Docker Ship') {
        sh 'docker push iaadefm/laravel:$BUILD_NUMBER'
    }
    
    stage('Docker Clean') {
        sh 'docker rmi -f iaadefm/laravel:$BUILD_NUMBER'
    }
}
