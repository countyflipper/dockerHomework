# Part 3

*	PS C:\Users\sderosa\Homework1\dockerHomework> kubectl apply -f bb.yaml
*	deployment.apps/bb-demo created
*	service/bb-entrypoint created
*	PS C:\Users\sderosa\Homework1\dockerHomework> kubectl get deployments
*	NAME      READY   UP-TO-DATE   AVAILABLE   AGE
*	bb-demo   1/1     1            1           15s
*	PS C:\Users\sderosa\Homework1\dockerHomework> kubectl get services
*	NAME            TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
*	bb-entrypoint   NodePort    10.98.141.243   <none>        8080:30001/TCP   26s
*	kubernetes      ClusterIP   10.96.0.1       <none>        443/TCP          151m
*	PS C:\Users\sderosa\Homework1\dockerHomework> kubectl delete -f bb.yaml
*	deployment.apps "bb-demo" deleted
*	service "bb-entrypoint" deleted
*	PS C:\Users\sderosa\Homework1\dockerHomework>
