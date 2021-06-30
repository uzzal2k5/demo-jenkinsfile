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
//         def i = 0
 for (int i = 0; i < repo.size() ; i++){
      
//         while (i < repo.size()){
            name = repo[i].name
            branch  = repo[i].branch
            url  = repo[i].url
  def repobuildJob[name] = repobuild.collectEntries(){
             [stage("${name}") {
                print("repo" + i + " = " + name + ", " + "branch" + i + " = " + branch + "," + "url" + i + " = " + url)
                sleep 10     
               }]
        
            }
    
        }  //For Loop (*While Loop)
  parallel repobuildJob
}
 

}
