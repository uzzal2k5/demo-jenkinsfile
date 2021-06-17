#!/usr/bin/env groovy
@Library('pipeline-library-demo')
import com.packages.*
import groovy.json.JsonSlurper
import groovy.json.JsonSlurperClassic
//@Grab('org.yaml:snakeyaml:1.17')
//import org.yaml.snakeyaml.Yaml
//import org.yaml.snakeyaml.DumperOptions
//import static org.yaml.snakeyaml.DumperOptions.FlowStyle.BLOCK

//import com.packages.GlobalClass
//import com.packages.MultiFunction
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
    def i = 0
    while (i < repo.size()){
      name = repo[i].name
      branch = repo[i].branch
      url = repo[i].url
      i = i+1
     print("Build Number [" + i + "] with Repository: "+ name + " Branch: "+branch+" URL: "+ url)
    } 
}
 
}
