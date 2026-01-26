pipeline {
agent any
stages {
stage('Build') {
steps {
sh 'npm install'
sh 'npm run build'
}
}
stage('Deploy') {
steps {
withCredentials([string(credentialsId: 'netlify-api-key', variable: 'NETLIFY_AUTH_TOKEN')]) {
sh 'npx netlify deploy --prod --auth $NETLIFY_AUTH_TOKEN --dir=build'
}
}
}
}
}

