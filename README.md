# kubernetes+calico集群搭建相关配置

1、注意相关的配置文件，有可能是配置错误，比如加了不必要的双引号等kubectl get nodes应该能找到注册的节点信息

2、使用calico时，根据官方文档配置，注意policy-controller.yaml文件中的etcd配置，节点需要能访问到

3、使用calico时，节点上的kubelet注册服务信息需要标明Requires=calico-node.service等

4、calico在master上可以通过
calicoctl node show
calicoctl status
calicoctl pool show
等命令操作

5、查看日志，可以找到很多有用的信息，一般配置在/var/logs/kubernetes目录下，master日志可能有些实验性的特性加入进来导致controller和scheduler报错，暂时不用管

6、查看集群状态可以通过kubectl get cs
