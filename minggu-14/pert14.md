# ======= <h1>
> Nama: Achmad Syarif Abdullah
> NIM: 175610099
### ======= <h3>

### Step 1 Check application configuration <h3>
Let’s verify that the application we deployed in the previous scenario is running. We’ll use the kubectl get command and look for existing Pods:
   ![GitHub Logo](/minggu-14/Gambar/1.PNG)

If no pods are running then it means the interactive environment is still reloading it's previous state. Please wait a couple of seconds and list the Pods again. You can continue once you see the one Pod running.

Next, to view what containers are inside that Pod and what images are used to build those containers we run the describe pods command:
    ![GitHub Logo](/minggu-14/Gambar/2.PNG)

We see here details about the Pod’s container: IP address, the ports used and a list of events related to the lifecycle of the Pod.

The output of the describe command is extensive and covers some concepts that we didn’t explain yet, but don’t worry, they will become familiar by the end of this bootcamp.

Note: the describe command can be used to get detailed information about most of the kubernetes primitives: node, pods, deployments. The describe output is designed to be human readable, not to be scripted against.

### Step 2 Show the app in the terminal <h3>
Recall that Pods are running in an isolated, private network - so we need to proxy access to them so we can debug and interact with them. To do this, we'll use the kubectl proxy command to run a proxy in a second terminal window. Click on the command below to automatically open a new terminal and run the proxy:
    ![GitHub Logo](/minggu-14/Gambar/3.PNG)

echo -e "\n\n\n\e[92mStarting Proxy. After starting it will not output a response. Please click the first Terminal Tab\n"; kubectl proxy

Now again, we'll get the Pod name and query that pod directly through the proxy. To get the Pod name and store it in the POD_NAME environment variable:
    ![GitHub Logo](/minggu-14/Gambar/4.PNG)

export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
echo Name of the Pod: $POD_NAME

To see the output of our application, run a curl request.
    ![GitHub Logo](/minggu-14/Gambar/5.PNG)

The url is the route to the API of the Pod.

### Step 3 View the container logs <h3>
Anything that the application would normally send to STDOUT becomes logs for the container within the Pod. We can retrieve these logs using the kubectl logs command:
    ![GitHub Logo](/minggu-14/Gambar/6.PNG)

Note: We don’t need to specify the container name, because we only have one container inside the pod.

### Step 4 Executing command on the container <h3>
We can execute commands directly on the container once the Pod is up and running. For this, we use the exec command and use the name of the Pod as a parameter. Let’s list the environment variables:
    ![GitHub Logo](/minggu-14/Gambar/7.PNG)

Again, worth mentioning that the name of the container itself can be omitted since we only have a single container in the Pod.

Next let’s start a bash session in the Pod’s container:
    ![GitHub Logo](/minggu-14/Gambar/8.PNG)

We have now an open console on the container where we run our NodeJS application. The source code of the app is in the server.js file:
    ![GitHub Logo](/minggu-14/Gambar/10.PNG)

You can check that the application is up by running a curl command:
    ![GitHub Logo](/minggu-14/Gambar/11.PNG)

Note: here we used localhost because we executed the command inside the NodeJS Pod. If you cannot connect to localhost:8080, check to make sure you have run the kubectl exec command and are launching the command from within the Pod

To close your container connection type exit.
    ![GitHub Logo](/minggu-14/Gambar/9.PNG)

