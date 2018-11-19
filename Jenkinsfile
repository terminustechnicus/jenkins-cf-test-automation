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
                sh 'python --version'
                sh 'python3 --version'
               // sh 'export PATH=~/.local/bin:$PATH'
              //  sh 'sudo pip --version'
              //  sh 'sudo pip install awscli --upgrade --user'
              //  sh 'aws --version'
            }
        }
    }
}
