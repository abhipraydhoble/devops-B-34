# Docker
![image](https://github.com/abhipraydhoble/devops-B-34/assets/122669982/7fcb6dc3-dfcd-4a00-9349-91b16869bd39)

**1. Developement Team:** Responsible for writing code

**2. Testing/QA Team:** Responsible for Testing code

**3. DevOps/Operations Team:** Responsible for providing infrastructure setup
   
- So all the code is stored or integrated inside github
- we cant deliver code to client directly
- we need to test this code
- so developers will test the code on machine/server where we need to install dependencies like
    - angular-frontend
    - java -backend
    - database server
    - tomcat for app
  so this set up we called as environment

- there are multliple environments present in a project such as
  
  **1. Dev** : Where developers write and test code.
  
  **2. Test** : Where testers ensure the code works correctly
  
  **3. UAT (User Acceptance Testing)** : Where customer will test the product
  
  **4. Prod** : Where the final product runs for end-users.

- install dependencies and particular version of software is a very difficult task
- to avoid these kind of environmental issues we are using docker
- whatever the software we required is install using docker
- 
Que. What is Docker?
**Docker** is an open source platform for developing, shipping and running applications in containers
           containers are lightweight, isolated environments that package application and their dependencies together.
  
  **Benefits**
  - portability
  - scalability
  - consistency
  - resource efficiency


  ## On-Premises vs. Virtual Machines (VMs)

| Feature                    | On-Premises                                      | Virtual Machines (VMs)                          |
|----------------------------|--------------------------------------------------|-------------------------------------------------|
| **Infrastructure**         | Physical servers located on-site                | Virtualized servers hosted either locally or in the cloud |
| **Initial Cost**           | High upfront investment in hardware             | Lower initial cost, pay-as-you-go model         |
| **Maintenance**            | Requires in-house IT staff for maintenance      | Managed by cloud providers or minimal local maintenance |
| **Scalability**            | Limited by physical hardware capacity           | Highly scalable, easy to add or remove resources |
| **Deployment Time**        | Longer, due to hardware setup and configuration | Faster, almost instant deployment               |
| **Control**                | Full control over hardware and software         | Control over virtual instances, less over physical hardware |
| **Security**               | Physical security controlled by the organization| Security managed by provider, with shared responsibility model |
| **Performance**            | High performance, no virtualization overhead    | Potential slight overhead due to virtualization |
| **Disaster Recovery**      | Requires in-house backup solutions              | Often includes built-in backup and recovery options |
| **Flexibility**            | Less flexible, tied to physical hardware        | More flexible, can easily reconfigure resources |
| **Updates**                | Manual updates required                         | Automated updates and patches provided by provider |
| **Energy Efficiency**      | Organization responsible for energy consumption | Energy efficiency managed by provider           |
| **Location Dependency**    | Must be managed on-site                         | Accessible from anywhere with internet access   |





## Virtual Machines (VMs) vs. Containers

| Feature                   | Virtual Machines (VMs)                               | Containers                                     |
|---------------------------|------------------------------------------------------|------------------------------------------------|
| **Architecture**          | Includes the entire OS, virtual hardware, and application | Shares the host OS kernel, includes only the application and its dependencies |
| **Size**                  | Typically large, includes full OS                   | Lightweight, usually in MBs                    |
| **Startup Time**          | Slower, can take minutes                            | Fast, usually in seconds                       |
| **Performance**           | Potential overhead due to full OS virtualization    | Near-native performance, minimal overhead      |
| **Isolation**             | Strong isolation, each VM has its own OS            | Process-level isolation, shares OS kernel      |
| **Resource Efficiency**   | Less efficient, more resources required per VM      | Highly efficient, better resource utilization  |
| **Portability**           | Portable across different environments, but larger in size | Highly portable, easy to move and replicate   |
| **Management**            | Requires hypervisor (e.g., VMware, Hyper-V)         | Requires container runtime (e.g., Docker)      |
| **Deployment Speed**      | Slower deployment due to full OS boot               | Rapid deployment                               |
| **Scalability**           | Scalable, but with more overhead and complexity     | Highly scalable with orchestration tools (e.g., Kubernetes) |
| **Security**              | Strong isolation with separate OS instances         | Shared kernel can pose security risks, but improving |
| **Use Cases**             | Running multiple OS environments, legacy application support | Microservices, agile development, continuous integration/continuous deployment (CI/CD) |
| **Storage**               | Each VM has its own storage                         | Containers can share storage volumes           |
| **Networking**            | Requires network bridging or virtual netwo








![docker architecture](https://github.com/abhipraydhoble/devops-B-34/assets/122669982/5f9d4992-8282-4bd5-8e3f-640e715c737c)


## Installation

````
sudo yum update -y
sudo yum install -y docker
sudo service docker start
sudo usermod -a -G docker ec2-user
````
````
docker --version
````

# Virtual Machines (VMs) vs. Containers

<table>
  <thead>
    <tr>
      <th style="color:blue">Feature</th>
      <th style="color:green">Virtual Machines (VMs)</th>
      <th style="color:purple">Containers</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Architecture</td>
      <td>Includes the entire OS, virtual hardware, and application</td>
      <td>Shares the host OS kernel, includes only the application and its dependencies</td>
    </tr>
    <tr>
      <td>Size</td>
      <td>Typically large, includes full OS</td>
      <td>Lightweight, usually in MBs</td>
    </tr>
    <tr>
      <td>Startup Time</td>
      <td>Slower, can take minutes</td>
      <td>Fast, usually in seconds</td>
    </tr>
    <tr>
      <td>Performance</td>
      <td>Potential overhead due to full OS virtualization</td>
      <td>Near-native performance, minimal overhead</td>
    </tr>
    <tr>
      <td>Isolation</td>
      <td>Strong isolation, each VM has its own OS</td>
      <td>Process-level isolation, shares OS kernel</td>
    </tr>
    <tr>
      <td>Resource Efficiency</td>
      <td>Less efficient, more resources required per VM</td>
      <td>Highly efficient, better resource utilization</td>
    </tr>
    <tr>
      <td>Portability</td>
      <td>Portable across different environments, but larger in size</td>
      <td>Highly portable, easy to move and replicate</td>
    </tr>
    <tr>
      <td>Management</td>
      <td>Requires hypervisor (e.g., VMware, Hyper-V)</td>
      <td>Requires container runtime (e.g., Docker)</td>
    </tr>
    <tr>
      <td>Deployment Speed</td>
      <td>Slower deployment due to full OS boot</td>
      <td>Rapid deployment</td>
    </tr>
    <tr>
      <td>Scalability</td>
      <td>Scalable, but with more overhead and complexity</td>
      <td>Highly scalable with orchestration tools (e.g., Kubernetes)</td>
    </tr>
    <tr>
      <td>Security</td>
      <td>Strong isolation with separate OS instances</td>
      <td>Shared kernel can pose security risks, but improving</td>
    </tr>
    <tr>
      <td>Use Cases</td>
      <td>Running multiple OS environments, legacy application support</td>
      <td>Microservices, agile development, continuous integration/continuous deployment (CI/CD)</td>
    </tr>
    <tr>
      <td>Storage</td>
      <td>Each VM has its own storage</td>
      <td>Containers can share storage volumes</td>
    </tr>
    <tr>
      <td>Networking</td>
      <td>Requires network bridging or virtual networks</td>
      <td>Lightweight network overlays, easier service discovery</td>
    </tr>
    <tr>
      <td>Boot Time</td>
      <td>Slower, similar to physical machines</td>
      <td>Very fast, almost instant</td>
    </tr>
  </tbody>
</table>
