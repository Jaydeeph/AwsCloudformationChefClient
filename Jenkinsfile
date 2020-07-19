#!/usr/bin/env groovy

@Library('github.com/releaseworks/jenkinslib') _

node {
  stage("Create Cloudformation Stack") {
    withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'aws-key', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY']]) {
        AWS("cloudformation create-stack --stack-name chef-client-test --template-body file://create_client_instance.yaml --region 'us-east-1'")
    }
  }
} 