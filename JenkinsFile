podTemplate(containers: [
    containerTemplate(name: 'nodejs', image: 'node:20', command: 'cat', ttyEnabled: true)
]) {
    node(POD_LABEL) {
        stage('Install Dependencies') {
            container('nodejs') {
                sh 'npm install'
            }
        }
        
        stage('Run Tests') {
            container('nodejs') {
                sh 'npm test'
            }
        }
        
        stage('Build') {
            container('nodejs') {
                sh 'npm run build'
            }
        }
        
        stage('Package') {
            container('nodejs') {
                sh 'npm pack'
            }
        }
    }
}
