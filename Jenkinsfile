#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage("checkout") {
            steps {
                checkout scm
            }
        }
        stage("setup env") {
            steps {
                sh '''
                if test ! -d .virtualenv; then
                    virtualenv --python=python3 .virtualenv
                fi
                . .virtualenv/bin/activate
                pip install -r requirements-dev.txt
                '''
            }
        }
        stage("test") {
            steps {
                sh '''
                . .virtualenv/bin/activate
                tox
                '''
            }
        }
        stage("dist") {
            steps {
                sh '''
                . .virtualenv/bin/activate
                python setup.py sdist
                '''
            }
        }
    }
    post {
        always {
            junit 'results.xml'
            archiveArtifacts artifacts: 'dist/*.tar.gz'
        }
    }
}