Kubernetes Components
=====================


NODE
----

Nodes are the primary compent of a Kubernetes cluster. We will talk about the two types of nodes found in every cluster. A *worker node* and a *leader node*.
You will see the leader node referred to by different names (depending on documentation) but the process is all the same. Nodes can be bare metal, virtual
machines, or even containers (used in development use cases). Worker nodes will run your containerized workloads while the leader nodes will handle 
scheduling of where workloads will be deployed, configuration and state of the cluster. 

In this course, the cluster is already set up for you. You will communicate with the leader node to perform all actions for this course. The Kubernetes 
specific command-line tool you'll use is *kubectl*. Kubectl allows you to view, configure, inspect all aspects of the cluster.

Let's view the nodes attached to our cluster by connecting to the Jumphost from within the lab environment. 

.. image:: images/access_jump.png


.. code-block:: bash 
   :caption: Get node info

   kubectl get nodes 

.. code-block:: 
   :caption: Node data basic 

    NAME                       STATUS   ROLES                  AGE    VERSION
    k3s-master.agility.lab     Ready    control-plane,master   308d   v1.25.6+k3s1
    k3s-worker-2.agility.lab   Ready    <none>                 308d   v1.25.6+k3s1
    k3s-worker-1.agility.lab   Ready    <none>                 308d   v1.25.6+k3s1


That was very basic information on our nodes, but if we want more details we can add the `-o` for *output* and add *wide*

.. code-block:: bash 
   :caption: Get node info wide 

   kubectl get nodes -o wide

.. code-block:: 
   :caption: Node data wide 

    NAME                       STATUS   ROLES                  AGE    VERSION        INTERNAL-IP   EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION    CONTAINER-RUNTIME
    k3s-master.agility.lab     Ready    control-plane,master   308d   v1.25.6+k3s1   10.1.1.5      <none>        Ubuntu 20.04.5 LTS   5.15.0-1030-aws   containerd://1.6.15-k3s1
    k3s-worker-2.agility.lab   Ready    <none>                 308d   v1.25.6+k3s1   10.1.1.7      <none>        Ubuntu 20.04.5 LTS   5.15.0-1030-aws   containerd://1.6.15-k3s1
    k3s-worker-1.agility.lab   Ready    <none>                 308d   v1.25.6+k3s1   10.1.1.6      <none>        Ubuntu 20.04.5 LTS   5.15.0-1030-aws   containerd://1.6.15-k3s1

Namespaces
----------


POD 
---


