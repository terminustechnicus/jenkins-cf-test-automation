/*
 * Copyright 2014 Yoyodyne, Inc.
 */
// FIXME write this
/*
stage('pre-create') {
    node {
        echo "pre-create stack stage"
    }
}

stage('create') {
    node {
        echo "create stack stage"
    }
}

stage('post-create') {
    node {
        echo "post-create stack stage"
    }
}
*/
/*
pipeline {
    agent {
        docker { image 'centos:latest' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'python --version'
                sh 'whoami'
                sh 'curl -O https://bootstrap.pypa.io/get-pip.py'
                sh 'python get-pip.py --user'
                sh 'export PATH=~/.local/bin:$PATH'
                sh ' pip install awscli --upgrade --user'
                sh 'aws --version'
            }
        }
    }
}
*/
node {
 
 docker.image('centos:latest').inside() {
           
            sh 'whoami'
        }   
    
}
