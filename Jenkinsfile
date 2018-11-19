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
pipeline {
    agent {
        docker { image 'amazonlinux' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'curl -O https://bootstrap.pypa.io/get-pip.py'
                sh 'python get-pip.py'
                sh 'export PATH=~/.local/bin:$PATH'
                sh 'pip --version'
                sh 'pip install awscli --upgrade'
                sh 'aws --version'
            }
        }
    }
}
