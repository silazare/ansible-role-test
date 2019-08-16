properties ([
    disableConcurrentBuilds(),
    buildDiscarder(logRotator(numToKeepStr: '10', daysToKeepStr: '7')),
    pipelineTriggers([pollSCM('H/2 * * * *')]),
])

node() {
    def MOLECULE_VERSION = '2.22rc6'
    def ANSIBLE_VERSION = '2.8.3'
    def DEBUG = false

    try {
        stage ("Checkout") {
            checkout scm
            ansiColor('xterm') {
                sh 'git rev-parse HEAD > .git/commit-id'
            }    
        }
        stage ("Install Application Dependencies") {
            ansiColor('xterm') {
                sh "sudo pip install --upgrade ansible==${ANSIBLE_VERSION} molecule==${MOLECULE_VERSION} docker"
            }
        }
        stage ("Molecule lint") {
            ansiColor('xterm') {
                if ("${DEBUG}") {
                    sh 'molecule --debug lint'
                }
                else {
                    sh 'molecule lint'
                }
            }
        }
        stage ("Molecule create") {
            ansiColor('xterm') {
                if ("${DEBUG}") {
                    sh 'molecule --debug create'
                }
                else {
                    sh 'molecule create'
                }
            }
        }
        stage ("Molecule converge") {
            ansiColor('xterm') {
                if ("${DEBUG}") {
                    sh 'molecule --debug converge'
                }
                else {
                    sh 'molecule converge'
                }
            }
        }
        stage ("Molecule idemotence") {
            ansiColor('xterm') {
                if ("${DEBUG}") {
                    sh 'molecule --debug idempotence'
                }
                else {
                    sh 'molecule idempotence'
                }
            }
        }
        stage ("Molecule verify") {
            ansiColor('xterm') {
                if ("${DEBUG}") {
                    sh 'molecule --debug verify'
                }
                else {
                    sh 'molecule verify'
                }
            }
        }
        stage ("Molecule destroy") {
            ansiColor('xterm') {
                if ("${DEBUG}") {
                    sh 'molecule --debug destroy'
                }
                else {
                    sh 'molecule destroy'
                }
            }
        }
    } catch(all) {
        currentBuild.result = "FAILURE"
        //throw err
    }
}
