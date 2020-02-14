#Part 4

PS C:\Users\sderosa\Homework1\dockerHomework> docker system info
Client:
 Debug Mode: false

Server:
 Containers: 20
  Running: 18
  Paused: 0
  Stopped: 2
 Images: 16
 Server Version: 19.03.5
 Storage Driver: overlay2
  Backing Filesystem: extfs
  Supports d_type: true
  Native Overlay Diff: true
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
 Swarm: active
  NodeID: pki1kcgcj79wkidvrs38sy9bu
  Is Manager: true
  ClusterID: jz1umgqn43zk09g24onc9w926
  Managers: 1
  Nodes: 1
  Default Address Pool: 10.0.0.0/8
  SubnetSize: 24
  Data Path Port: 4789
  Orchestration:
   Task History Retention Limit: 5
  Raft:
   Snapshot Interval: 10000
   Number of Old Snapshots to Retain: 0
   Heartbeat Tick: 1
   Election Tick: 10
  Dispatcher:
   Heartbeat Period: 5 seconds
  CA Configuration:
   Expiry Duration: 3 months
   Force Rotate: 0
  Autolock Managers: false
  Root Rotation In Progress: false
  Node Address: 192.168.65.3
  Manager Addresses:
   192.168.65.3:2377
 Runtimes: runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: b34a5c8af56e510852c35414db4c1f4fa6172339
 runc version: 3e425f80a8c931f88e6d94a8c831b9d5aa481657
 init version: fec3683
 Security Options:
  seccomp
   Profile: default
 Kernel Version: 4.19.76-linuxkit
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 2
 Total Memory: 1.919GiB
 Name: docker-desktop
 ID: RM56:CQNE:NU5P:HSLN:PCTI:4USY:GWTW:U2NO:BWAS:MW6N:JNZY:LAPW
 Docker Root Dir: /var/lib/docker
 Debug Mode: true
  File Descriptors: 147
  Goroutines: 240
  System Time: 2020-02-14T00:17:53.468567568Z
  EventsListeners: 3
 Registry: https://index.docker.io/v1/
 Labels:
 Experimental: false
 Insecure Registries:
  127.0.0.0/8
 Live Restore Enabled: false
 Product License: Community Engine

PS C:\Users\sderosa\Homework1\dockerHomework> docker stack deploy -c bb-stack.yaml demo
Creating network demo_default
Creating service demo_bb-app
PS C:\Users\sderosa\Homework1\dockerHomework> docker service ls
ID                  NAME                MODE                REPLICAS            IMAGE               PORTS
1j337bavgpqb        demo_bb-app         replicated          1/1                 bulletinboard:1.0   *:8000->8080/tcp
PS C:\Users\sderosa\Homework1\dockerHomework> docker stack rm demo
Removing service demo_bb-app
Removing network demo_default
PS C:\Users\sderosa\Homework1\dockerHomework>