The Path to Understanding Kubernetes and Containers - Intro
-----------------------------------------------------------

Purpose:


*Containers* slightly resemble virtual machines. In that, they contain file systems, all necessary libraries, and will use portions of memory and compute
from the host. Containers can allow you to build and move applications nearly anywhere and are usually lightweight. Being that they are lightweight, 
this allows you to maintain different environments (dev, qa, production) and have full application functionality.

*Kubernetes* originates from Greek, meaning pilot or helmsman. It's an open source platform used in managing containerized workloads and services. Kubernetes
is an *orchestration* tool ensuring containerized workloads are available and scalable. And since its power is in orchestration this relieves admins from the burden
of many manual processes to keep applications available and push updates.

What Kubernetes is **NOT**:
 - Hypervisor or Operating System
 - Replacement for container runtime (i.e. Docker)
 - Just for Microservices
 - Standalone solution

What Kubernetes **IS**:
 - Orchestration Platform (ensuring workloads are available/scalable)
 - Ideal for microservices 
 - Enables *cloud native* application design

The evolution off applications from baremetal servers, to virtual servers and now containers. Each one of these technologies serves its purpose and moving to the latest and greatest
is not always the answer. There are, however, some definate advantages to a container based evnironment. In the *Container Deployment* image you can see we are no longer
bound to the operating system, you can set resource limits per container and application dependencies are all built with the container image. Since the container houses
the application and its dependencies, this allows for easier upgrades and security fixes to your application.

.. image:: images/container_evo.png
   :width: 800
   :align: center
   :alt: Container Evolution


Official Kubernetes Documentation
---------------------------------

Feel free to use the official documentation to clarify information or dive deeper in this lab:

- `Kubectl Commands <https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands>`_
- `Kubernetes Documentation <https://kubernetes.io/docs/home/>`_
- `Kubernetes Nodes <https://kubernetes.io/docs/concepts/architecture/nodes/>`_
- `Kubernetes Custom Resource <https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/>`_


Lab Inventory
-------------

.. list-table:: 
  :header-rows: 1

  * - **Instance**
    - **IP Address**
    - **OS**
    - **NGINX Services**
    - **Apps/Protocols**
  * - k3s Leader Node
    - 10.1.1.5
    - Ubuntu 20.04 LTS
    - NIC
    - SSH, k3s
  * - k3s Worker Node 1
    - 10.1.1.6
    - Ubuntu 20.04 LTS
    - NIC
    - SSH, k3s, Arcadia Finance
  * - k3s Worker Node 2
    - 10.1.1.7
    - Ubuntu 20.04 LTS
    - NIC
    - SSH, k3s, Arcadia Finance
  * - NGINX Plus 1
    - 10.1.1.8
    - Ubuntu 20.04 LTS
    - Plus + NAP
    - SSH
  * - NGINX Plus 2
    - 10.1.1.9
    - Ubuntu 20.04 LTS
    - Plus
    - SSH
  * - DevOps Tools
    - 10.1.1.10
    - Ubuntu 20.04 LTS
    - none
    - SSH

Accessing the Lab
-----------------

In this lab, you can access resources by connecting to a Linux jump host running XRDP or from a web shell. XRDP is an open-source version of the popular Remote Desktop Protocol and is compatible with all popular RDP clients.

When you first connect to the Jump Host via RDP, you will be prompted to click **OK** to connect to the remote session.

.. image:: images/xrdp_login_prompt.png

Once connected, you will see the desktop as shown below.

.. image:: images/xrdp_desktop.png

Clicking on the **Applications** drop-down in the menu bar will bring up a list of applications you will need to finish this lab.

**Favorites** includes Firefox, Visual Studio Code and Terminal.

.. image:: images/desktop_favorites.png

**SSH Shortcuts** open SSH terminal windows to the command prompt of all machines in the lab.

.. image:: images/desktop_ssh.png

Each section in this lab will begin with the assumption that you are connected via RDP, able to navigate the **Applications** menu and familiar with the available applications.

Remember these important tips:

- Lab modules are independent; feel free to tackle the modules in any order.
- The username **lab** and password **f5Appw0rld!** will work for every login unless specifically noted.
- Traffic and attack generators are running to help generate statistics, events and attacks.
- To paste text into the lab, right-click your mouse and select **Paste** as keyboard shortcuts are not consistent between applications.
- The screen resolution for the Remote Desktop connection is selected when connecting to the session. Choose a resolution that works best for you.

.. note:: To allow for easy reference back to this page, hold CTRL (Windows) or CMD (Mac) while clicking the **Next** button below to continue in a new tab.

To access by web shell 

.. image:: images/jumphost_webshell.png