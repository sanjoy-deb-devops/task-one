* Run the docker compose up from the Jenkinsfile directory
`docker compose up -d`
* Develop the laravel appliction under the src directory
* Build the new image from Dockerfile under build directory
`docker build -t username/reponame:tag`
* Login Docker hub and push the new image to Docker hub
~~~
docker login
docker push <hub-user>/<repo-name>:<tag>
~~~
* To scale up we need to edit scale parameter to desire size of the nginx or app01/02 kubernetes deployment yaml
* Alternatively we can run kubectl command to scale the target deployemnt 
`kubectl scale --replicas=<expected_replica_num> deployment <deployment_label_name> -n <namespace>`
