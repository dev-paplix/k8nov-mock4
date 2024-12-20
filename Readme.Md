Name:

Q1:

Taint your worker node to key1=value1 with NoSchedule. Create Deployment from Nginx Image in qq1 namespace and tolerate it to the worker node.

Q2:

Create a StatefulSet named database in qq3 namespace. use two images in the same StatefulSet one is mongo and another is mongo-express. The following mongo-express enviromental variables should come from configset:

      ME_CONFIG_MONGODB_URL: mongodb://root:example@mongo:27017/
      ME_CONFIG_BASICAUTH: false

And the following variables for mongo should come from secret:

      MONGO_INITDB_ROOT_USERNAME: 
      MONGO_INITDB_ROOT_PASSWORD:

You should use the same secret for the following variables for mongo-express:

      ME_CONFIG_MONGODB_ADMINUSERNAME: 
      ME_CONFIG_MONGODB_ADMINPASSWORD: 

Q3:

Create a new storageset and claim 3Gi of it by the database StatefulSet you created in the last question. Also this shoud have a mountPath of /etc/mongo


Q4:

Expand the database stateful set horizontaly to 5 Replicas


Q5:

Update your Kubeadm to v1.31.1. drain the nodes except DaemonSets and let the upgrade to be applied to enitre cluster.

Q6:

Deploy a pod named nginx using the nginx image in the qq3 namespace with a liveness and readiness probe for port 80.

Pod: nginx Namespace: qq3Image: nginx Liveness Probe: port: 80 Readiness Probe: port:80

Q7:

label your worker node to team=devops and create a deployment with an nginx image with 6 replicas in qq2 namespace to be deployed on that node. 



Q8:

Create a new role names examinee and bind it to entire cluster. Then create a deployment names apache use httpd image using examinee in namespace examinee


Q9:

Create a new deployment names frontend and deploy it on qq4 namespace with 4 replicas. You should use httpd:latest image. Update the image to httpd:bookworm and create a backup in etcd then rollout it back again to httpd:latest. Use the etcd backup to return it to httpd:bookworm.


Q10:

Create a new deployment and service names dashboard in qq5 namespace. Use the following image to deploy it:

drupal:10.2.7-php8.2-fpm-bookworm

The deployment shoud be accessible publicly in port 8080


Q11:

Create a new deployment in qq6 namespace names realtime with redis:latest image. Asign resources of CPU: 0.5 Memory: 500M for both limit and request  


Q12:

Create a persistent volume which has 10Gi, claim it by 3 deployments nginx:latest, httpd:latest, and postgres:12.20-bullseye



Q13:

Make a deployment of an image hashicorp/terraform in qq7 namespace with no environmental variable. Let the manager know the reason of the deployment failure 

Q14:

Create a deployment names http in the nameserver of qq8 with an image of traefik/whoami. The resource must be available from anywhere with port 8080

Q15:


Configure Horizontal Pod Autoscaling for a Deployment to automatically scale based on CPU usage.

Deployment Name: api-server
Namespace: production
Replica Set: Set initially to 2 replicas.
Container Image: nginx:1.18
CPU Target: Scale the Deployment if the average CPU usage exceeds 50%.
Minimum Pods: 2
Maximum Pods: 5


Q16:

Create a new pod names alpine with an image of alpine:edge in qq9 namespace. use the add the following command to the pod:

["sh", "-c", "while true; do echo 'Hello Alpine'; sleep 3; done"]

Take a screenshot of the pod echoing 'Hello Alpine'

Q17:

Create a deployment with 2 replicas from nginx:latest image in qq10 namespace. Make it available globally in whatever port randomly chosen. 


