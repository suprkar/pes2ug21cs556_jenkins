pipeline{
    agent any
    stages('Clone repository'){
        steps{
            checkout([$class: 'GitSCM',
            branches: [[name:'*/main']],
            userRemoteConfigs:[[url: 'https://github.com/suprkar/pes2ug21cs556_jenkins.git']]])
        }
    }
    stage('Build'){
        steps{
            build 'PES2UG21CS556-1'
            sh 'g++ main.cpp -o output'
        }
    }
    stage('Test'){
        steps{
            sh'./output'
        }
    }
    stage('Deploy'){
        steps{
            echo 'deploy'
        }
    }
    post{
    failure{
        error 'Pipeline failed'
    }
}

}
