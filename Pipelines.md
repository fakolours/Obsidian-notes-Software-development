Pipelines are written in [[Groovy]] for [[Jenkins]]. There are a few functions that are developed specifically for pipeline to be used in Jenkins. These functions will **NOT** be available in other interpreters than the Jenkins one. This will be important when using [[Shared Libraries]].
There are two types of pipelines : **SCRIPTED** and **DECLARATIVE**. If you are a beginner, you will prefer declarative ones.

## General knowledge about pipelines
Pipelines are divided in _stages_, which are used to divide your pipeline in small portions (really useful to read the logs).
A pipeline runs on a node, but with some command you can execute different _stages_ of a pipeline on different nodes.

Declarative and scripted pipelines are 2 really different way of coding. Declarative are more stable but they also are much more strict on the writing of the script.


## Declarative pipelines
Their structure is really stable. In the most simple case it would look like this :
```Groovy
pipeline{
	agent any
	stage('name of stage'){
		steps{
			//Actions you want to execute
		}
	}
}
```

The declarative pipelines prohibit the use of direct Groovy language, meaning you can't declare variables as you want or other things you might want to do. Every actions need to be wrapped. Such *wrappers* can be found in the following section **useful commands to include in pipeline**
## Scripted pipelines
## Useful commands to include in pipeline
- To execute commands (Executor is Windows):
	```Groovy
	bat(label:'name of your',script:'your script as in .bat file'){
		echo "Execute as in Windows console command"
	}
	```
		
```Groovy
	ps(label:'name of your',script:'your script as in .ps1 file'){
		Write "Execute as in Powershell"
	}
```
- To execute commands (Executor is under Linux):
```Groovy
	sh(label:'name of your',script:'your script as in .sh file'){
		echo "Execute as in Linux console command"
	}
```
## Specific knowledge about pipelines
