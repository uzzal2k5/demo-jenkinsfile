#!/usr/bin/env groovy
@Library('pipeline-library-demo')
import com.packages.*
import org.yaml.snakeyaml.*
import groovy.yaml.YamlSlurper
//Yaml parser = new Yaml()
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
stage('Read YAML File'){
    def yamlData =readYaml file: 'config.yaml'
    yamlData.withReader { reader ->
        // Use parse method of YamlSlurper.
        def yaml = new YamlSlurper().parse(reader)
        def param_name = yaml.parameter_new[0].name
        echo param_name;
    }

}
 stage('Global Class Funtion') {
   timestamps{
     logstash{
        echo 'Global CLass Library Implement'
        gclass.function1('Global CLass function1')
  
     }
   }
  

 }
