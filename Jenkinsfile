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
                sh 'uname -a'
            }
        }
    }
}
*/
stage('pre-create') {
    stage('Validate Template'){
        node {
            sh 'uname -a'
            sh 'pwd'
            sh 'ls'

            docker.image('centos:7').inside("-u root"){
             sh 'echo inside container'
             sh 'uname -a'
             sh 'whoami'
             sh 'curl -O https://bootstrap.pypa.io/get-pip.py'
             sh 'python get-pip.py --user'
             sh 'export PATH=~/.local/bin:$PATH'
             sh '/root/.local/bin/pip install awscli --upgrade --user'
             sh '/root/.local/bin/aws --version'
             sh '/root/.local/bin/aws cloudformation validate-template --template-body file://test-template.json --region us-east-1'
            }
        }   
    }
    stage('Lint Template'){
        node {
            docker.image('centos:7').inside("-u root"){
            sh 'yum  update -y'
            sh 'sudo yum install ruby -y'
            sh 'sudo yum install gcc g++ make automake autoconf curl-devel openssl-devel zlib-devel httpd-devel apr-devel apr-util-devel sqlite-devel -y'
            sh 'sudo yum install ruby-rdoc ruby-devel -y'
            sh 'yum install rubygems -y'
            sh 'gem install cfn-nag'
            sh 'cfn_nag_scan --input-path test-template.json'
            }
        }
    }      
}

stage('create') {
    node {
        echo "create stack stage"
    }
}

    
