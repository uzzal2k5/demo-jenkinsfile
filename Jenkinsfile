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
    println(data)
    println(data.parameter)
    println(data.parameter.repository)
    println(data.parameter.repository[0].name)
    println(data.parameter.repository[1].name)
    println(data.parameter.each{it.toString()})
    println(data.parameter.repository.each{it.toString()})
    def repo = data.parameter.repository.each{it.toString()}
    println "Repository"
    println repo
    println repo.size()
    def i = 0
    while (i < repo.size()){
      name = repo[i].name
      branch = repo[i].branch
      url = repo[i].url
     println "Build Repository Number : " i + 1
     print("Build with Repository: "+ name + " Branch: "+branch+" URL: "+ url)
    } 

 
}
 
}
