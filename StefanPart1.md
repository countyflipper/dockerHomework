#Part 1-1

PS C:\Users\sderosa> cd C:\Users\sderosa\Homework1
PS C:\Users\sderosa\Homework1> cd dockerHomework
PS C:\Users\sderosa\Homework1\dockerHomework> kubectl apply -f pod.yaml
error: unable to recognize "pod.yaml": Get https://kubernetes.docker.internal:6443/api?timeout=32s: dial tcp 127.0.0.1:6443: connectex: No connection could be made because the target machine actively refused it.
PS C:\Users\sderosa\Homework1\dockerHomework> kubectl apply -f pod.yaml
pod/demo created
PS C:\Users\sderosa\Homework1\dockerHomework> kubectl get pods
NAME   READY   STATUS    RESTARTS   AGE
demo   1/1     Running   0          15s
PS C:\Users\sderosa\Homework1\dockerHomework> kubectl logs demo
PING 8.8.8.8 (8.8.8.8): 56 data bytes
64 bytes from 8.8.8.8: seq=0 ttl=37 time=12.540 ms
64 bytes from 8.8.8.8: seq=1 ttl=37 time=12.269 ms
64 bytes from 8.8.8.8: seq=2 ttl=37 time=12.606 ms
64 bytes from 8.8.8.8: seq=3 ttl=37 time=12.743 ms
64 bytes from 8.8.8.8: seq=4 ttl=37 time=13.153 ms
64 bytes from 8.8.8.8: seq=5 ttl=37 time=13.140 ms
64 bytes from 8.8.8.8: seq=6 ttl=37 time=13.969 ms
64 bytes from 8.8.8.8: seq=7 ttl=37 time=13.399 ms
64 bytes from 8.8.8.8: seq=8 ttl=37 time=12.230 ms
64 bytes from 8.8.8.8: seq=9 ttl=37 time=11.734 ms
64 bytes from 8.8.8.8: seq=10 ttl=37 time=12.520 ms
64 bytes from 8.8.8.8: seq=11 ttl=37 time=12.292 ms
64 bytes from 8.8.8.8: seq=12 ttl=37 time=12.256 ms
64 bytes from 8.8.8.8: seq=13 ttl=37 time=12.456 ms
64 bytes from 8.8.8.8: seq=14 ttl=37 time=12.996 ms
64 bytes from 8.8.8.8: seq=15 ttl=37 time=12.247 ms
64 bytes from 8.8.8.8: seq=16 ttl=37 time=12.050 ms
64 bytes from 8.8.8.8: seq=17 ttl=37 time=78.282 ms
64 bytes from 8.8.8.8: seq=18 ttl=37 time=12.765 ms
64 bytes from 8.8.8.8: seq=19 ttl=37 time=12.641 ms
64 bytes from 8.8.8.8: seq=20 ttl=37 time=12.262 ms
64 bytes from 8.8.8.8: seq=21 ttl=37 time=13.109 ms
64 bytes from 8.8.8.8: seq=22 ttl=37 time=13.339 ms
PS C:\Users\sderosa\Homework1\dockerHomework> kubectl delete -f pod.yaml
pod "demo" deleted
PS C:\Users\sderosa\Homework1\dockerHomework>


#Part 1-2
PS C:\Users\sderosa> docker swarm init
error during connect: Post http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.40/swarm/init: open //./pipe/docker_engine: The system cannot find the file specified. In the default daemon configuration on Windows, the docker client must be run elevated to connect. This error may also indicate that the docker daemon is not running.
PS C:\Users\sderosa> docker swarm init
Swarm initialized: current node (pki1kcgcj79wkidvrs38sy9bu) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-25mtaw7hj4zasty35ax8kkou0h4vww37on09mfsmmqsrvyu1or-2wa180jnl8qubgtzany3nt0hz 192.168.65.3:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

PS C:\Users\sderosa> docker service create --name demo alpine:3.5 ping 8.8.8.8
20npsx4pgzcow1zhbsqxqdqez
overall progress: 1 out of 1 tasks
1/1: running   [==================================================>]
verify: Service converged
PS C:\Users\sderosa> docker service ps demo
ID                  NAME                IMAGE               NODE                DESIRED STATE       CURRENT STATE            ERROR               PORTS
pmgayxz6qy85        demo.1              alpine:3.5          docker-desktop      Running             Running 13 seconds ago
PS C:\Users\sderosa> docker service logs demo
demo.1.pmgayxz6qy85@docker-desktop    | PING 8.8.8.8 (8.8.8.8): 56 data bytes
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=0 ttl=37 time=12.089 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=1 ttl=37 time=12.862 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=2 ttl=37 time=12.020 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=3 ttl=37 time=12.217 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=4 ttl=37 time=12.577 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=5 ttl=37 time=13.184 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=6 ttl=37 time=22.260 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=7 ttl=37 time=12.481 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=8 ttl=37 time=12.964 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=9 ttl=37 time=24.794 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=10 ttl=37 time=12.136 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=11 ttl=37 time=12.429 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=12 ttl=37 time=12.729 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=13 ttl=37 time=13.183 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=14 ttl=37 time=48.735 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=15 ttl=37 time=11.669 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=16 ttl=37 time=12.442 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=17 ttl=37 time=12.209 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=18 ttl=37 time=12.337 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=19 ttl=37 time=12.911 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=20 ttl=37 time=12.304 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=21 ttl=37 time=12.373 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=22 ttl=37 time=12.659 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=23 ttl=37 time=13.102 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=24 ttl=37 time=13.037 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=25 ttl=37 time=12.947 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=26 ttl=37 time=12.919 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=27 ttl=37 time=12.816 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=28 ttl=37 time=12.946 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=29 ttl=37 time=12.647 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=30 ttl=37 time=13.459 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=31 ttl=37 time=12.491 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=32 ttl=37 time=12.250 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=33 ttl=37 time=12.988 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=34 ttl=37 time=12.853 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=35 ttl=37 time=12.963 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=36 ttl=37 time=12.639 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=37 ttl=37 time=12.023 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=38 ttl=37 time=12.103 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=39 ttl=37 time=12.970 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=40 ttl=37 time=13.084 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=41 ttl=37 time=12.129 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=42 ttl=37 time=12.740 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=43 ttl=37 time=12.948 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=44 ttl=37 time=12.931 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=45 ttl=37 time=12.483 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=46 ttl=37 time=11.440 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=47 ttl=37 time=12.404 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=48 ttl=37 time=12.158 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=49 ttl=37 time=13.356 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=50 ttl=37 time=11.988 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=51 ttl=37 time=13.046 ms
demo.1.pmgayxz6qy85@docker-desktop    | 64 bytes from 8.8.8.8: seq=52 ttl=37 time=12.996 ms
PS C:\Users\sderosa> docker service rm demo
demo
PS C:\Users\sderosa>