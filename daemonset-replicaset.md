
# DaemonSet vs ReplicaSet Usecase

    1. ReplicaSet
  
        -> ReplicasSet will ensure that the number of pods (defined in our config file) is always running in our cluster.
        -> It won't consider in which worker node they are running
        -> If any of the Pods goes down or deleted it will automatically replicate to match the desired count which we configured in the yaml file.
        
    2. DaemonSet
        -> DaemonSet will ensure that one copy of pod defined in our configuration will always be available on every worker node.
        -> Node count and Pod count will be considered in Daemonset.
        
