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
 stage('Variables') {
  echo 'Library Variables Class Implement'
  println GlobalClass.foo
 
 }

stage('Multi Funtion') {
  echo 'Multifunction Library Implement'
  gc.function1('function1')
  gc.function2('function2')
  gc.function3('function3')

 }
stage("Parse JSON ") {
//    def projects = readJSON file: "${env.WORKSPACE}\\Projects.json"
//    def  slurper = new JsonSlurperClassic()
//    def jobject =  slurper.parse('config.json')
    def restResponse = readFile(file: 'config.json')
    println(restResponse)
    def data = readJSON text: restResponse
    def repos = data.Parameters
    print(repos.parameter1_repo1[0].name)

}
// stage('Read YAML file 1') {
//     script{ datas = readYaml (file: "${env.WORKSPACE}/config.yaml") }
//     echo datas.Parameters[0].toString()
//     }
stage('Read YAML File'){
//    def val = this.context.readYaml file: "config.yaml"
//    this.parameter_new = val.parameter_new
//    print(this.parameter_new)
    def data = readYaml file: "config.yaml"
    println(data)
    println(data.parameter)
 
    println(data.parameter.parameter1_repo1)
    println(data.parameter.each{it.toString()})
 if (data != null){
  data.parameter.each{
   String repository = it.toString()
   repository.each{ key, value -> println key}
//            String repoName = repository['@']
//            println(repoName)
  }
 }
    
//     def name = repos[0].name
//     echo "${name}";

}
 
}
