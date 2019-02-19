
import groovy.json.JsonSlurperClassic


@NonCPS
def jsonParse(def json) {
    new groovy.json.JsonSlurperClassic().parseText(json)
}


  timeout(time: 25, unit: 'MINUTES') {

    def BUILD_NODE = 'workers'

    // Read project name as docker image
    def imageName = 'cgw.media.relay'

    // Base image [Major.minor.patch]
    def version

    // Custom label 'latest' for latest master builds or 'dev' for latest 'dev' builds
    def tag

    // Build tag for the docker image
    def buildTag

    // Docker Registry on Artifactory
    def registryHostname = 'watson-vg-docker-local.artifactory.swg-devops.com'
    def registryUrl = 'https://' + registryHostname
    node(BUILD_NODE){

    docker.withRegistry(registryUrl, 'vgwfun01') {

        stage('checkout'){
          checkout scm
        }

		stage('test') {
			sh 'echo "hello world!"'
		}
		}
	}
  }
