#!/usr/bin/env groovy
@Library('pipeline-library-demo')
import com.packages.*
import groovy.json.JsonSlurperClassic
//@Grab('org.yaml:snakeyaml:1.17')
//import org.yaml.snakeyaml.Yaml
//import org.yaml.snakeyaml.DumperOptions
//import static org.yaml.snakeyaml.DumperOptions.FlowStyle.BLOCK

//import com.packages.GlobalClass
//import com.packages.MultiFunction
def gclass = new GlobalClass()
def gc = new MultiFunction()
 
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
// stage("Parse JSON ") {
// //    def projects = readJSON file: "${env.WORKSPACE}\\Projects.json"
// //    def  slurper = new JsonSlurperClassic()
// //    def jobject =  slurper.parse('config.json')
//     def restResponse = readFile(file: 'config.json')
//     println(restResponse)
// //    def data = new JsonSlurper().parseText( restResponse )
//     def data = readJSON text: restResponse
//    print(data.parameter_new[0].name)

// }
// stage('Read YAML file 1') {
//     script{ datas = readYaml (file: "${env.WORKSPACE}/config.yaml") }
//     echo datas.Parameters[0].toString()
//     }
stage('Read YAML File'){
//    def val = this.context.readYaml file: "config.yaml"
//    this.parameter_new = val.parameter_new
//    print(this.parameter_new)
    def yamlData = readYaml file: "config.yaml"
    def param_name = yamlData.Parameter[0]
    echo "${param_name}";
//    echo param_name;
//    def ano_val = ${param_name}


}
 stage('Global Class Funtion') {
   timestamps{
     logstash{
        echo 'Global CLass Library Implement'
        gclass.function1('Global CLass function1')
  
     }
   }
  

 }


