node('linux') {
    try {
        stage('Hello') {
            echo "Hello World from AWS EC2!"
        }
        stage('Checkout') {
            checkout scmGit(branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Daviddager/commit-test.git']])
        }
        stage('List files') {
            sh "ls -oh"
        }
        withCredentials([string(credentialsId: 'git-username', variable: 'USERNAME')]) {
            stage('Get username') {
                sh "env | sort"
            }
        }
    } catch (error){
        throw error
    } finally {
        cleanWs()
    }
}
node('main') {
    echo "Hello from Jenkins leader"
}