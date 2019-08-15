# tektonexamples
Very simple Tekton examples to show the theory of the Pipeline integration into OCP

Three major components within Tekton from the usage perspective:

TASKS are individual executable components that operate on a container (individual uses of the tasks are TASKRUNS)
TASKPIPELINES are the pipelines that execute sequentially a set of TASKS
TASKPIPELINERUNS are the individual uses of the TASKPIPELINES

To try a basic example:

1: On a valid OCP4 cluster use the operatorhub catalog to install the OpenShift Pipelines Operator (across all namespaces)

2: Create a project (example 'pipelines')

3: Create the tasks (within this directory, 'oc create -f task1.yaml', 'oc create -f task2.yaml', 'oc create -f task3.yaml')

4: Use the 'oc get' to get the new Custom Resources - Operators extend the Object model of OCP, in this case you can do 'oc get tasks' which should display the three Tekton tasks you just created

5: Create the Pipeline definition using 'oc create -f taskPipeline.yaml'

6: Check the creation of the CR using 'oc get taskpipeline'

7: Now execute the Pipeline using Tekton - 'oc create -f taskPipelineRun.yaml'

8: Optional - you can use the tkn CLI if installed, this wraps the 'oc' and kubectl' commands in a useful way

9: If you then try 'oc get taskpipelineruns' you should see if the Pipeline has been successful or not 
