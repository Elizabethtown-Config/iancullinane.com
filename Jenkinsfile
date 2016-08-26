
git_creds = 'e6a36c15-1342-4105-9ef8-896857a5781c'
git_url = 'git@github.com:Elizabethtown-Config/'
project = 'iancullinane.com'
deploy_url = "${git_url}${project}.git"




node(NODE_LABEL){

    stage "Checkout"
    git branch: 'master', credentialsId: git_creds, url: deploy_url

    stage "Deploy"
    withEnv(["NODE_PORT=3334"]){
        sh "docker-compose up"
    }

    //sh 'pm2 start bin/www'
}