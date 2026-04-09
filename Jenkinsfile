node('linux') {
    try {
        stage('Hello') {
            echo "Hello World!"
        }
        stage('Checkout') {
            checkout scmGit(branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Daviddager/commit-test.git']])
        }
        stage('List files') {
            sh "ls -oh"
        }
    } catch (error){
        throw error
    } finally {
        cleanWs()
    }
}