#!/usr/bin/env groovy
@Library('pipeline-library-demo')
import com.packages.*
import groovy.json.JsonSlurper
import groovy.json.JsonSlurperClassic

def gclass = new GlobalClass()
def gc = new MultiFunction()
node { 
 stage('Checkout'){
 checkout([$class: 'GitSCM', branches: [[name: '*/read_from_yaml']], extensions: [], userRemoteConfigs: [[credentialsId: 'uzzal_sshkey_security_server', url: 'https://github.com/uzzal2k5/demo-jenkinsfile.git']]])}
 stage('Function') {
     echo 'Hello world'
     sayHello 'uzzal'

 }

stage('Read YAML File'){
        def data = readYaml file: "config.yaml"
        def repo = data.parameter.repository
        println "Repository"
        println repo
        println repo.size()
        def repobuild = [:]
        def i = 0
        while (i < repo.size()){
            name = repo[i].name
            branch  = repo[i].branch
            url  = repo[i].url
            repobuild["$i"] = {
              stage("${name+i}") {
                print("repo" + i + " = " + name + ", " + "branch" + i + " = " + branch + "," + "url" + i + " = " + url)
                sleep 10     
               }
             }
            i = i+1
//         parallel repobuild
        }  //while
    parallel repobuild
}
 
 stage("Parallel Work Stage") {

    // Prealocate dict/map of branchstages
    def branchedStages = [:]

    // Loop through all parallel branched stage names
    for (STAGE_NAME in ["Branch_1", "Branch_2", "Branch_3"]) {

        // Define and add to stages dict/map of parallel branch stages
        branchedStages["${STAGE_NAME}"] = {
            stage("Parallel Branch Stage: ${STAGE_NAME}") {
                // Parallel stage work here
                sh "sleep 10"
            }
        }

    }

    // Execute the stages in parallel
    parallel branchedStages
}
}
