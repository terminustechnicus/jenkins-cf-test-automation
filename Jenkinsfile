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
pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { image 'maven:3-alpine' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
