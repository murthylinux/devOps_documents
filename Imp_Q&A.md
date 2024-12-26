### **What’s the difference between continuous integration, continuous delivery, and continuous deployment?**

* ***Continuous integration (CI)*** executes the sequence of steps required to build and test the project. 
CI runs automatically on every change committed to a shared repository, offering developers quick feedback about the project’s state.

* ***Continuous delivery*** is an extension of CI. Its goal is to automate every step required to package and release a piece of software. 
The output of a continuous delivery pipeline takes the form of a deployable binary, package, or container.

* ***Continuous deployment*** is an optional step up from continuous delivery. 
It is a process that takes the output from the delivery pipeline and deploys it to the production system in a safe and automated way.


## **Kubernetes Deployment Strategy Types:**

1. **Rolling Deployment**
A Rolling Deployment strategy allows for a gradual update of the application by incrementally replacing old instances with new ones. This approach ensures minimal downtime as the new instances are gradually introduced while the old ones are gracefully terminated. Rolling deployments are ideal for applications that require high availability and continuous operations.

2. **Recreate Deployment**
In a Recreate Deployment strategy, the existing instances are terminated first, and then the new instances are created. This approach creates a brief period of downtime as the application is unavailable during the update process. Recreate deployments are suitable for applications that can tolerate short periods of unavailability or those where downtime can be scheduled during low-traffic periods.

3. **Ramped Slow Rollout**
The Ramped Slow Rollout strategy gradually ramps up the new version of an application by gradually increasing the percentage of traffic it receives. This approach allows for early detection of issues and provides a controlled way to monitor the performance of the new version. Ramped slow rollouts are beneficial for applications that require careful monitoring and verification before fully rolling out the update.

4. **Best-Effort Controlled Rollout**
The Best-Effort Controlled Rollout strategy allows for fine-grained control over the deployment process. It enables the operator to specify the desired number or percentage of pods to be updated at a given time. This approach provides flexibility while maintaining control over the update process, making it suitable for complex applications with specific deployment requirements.

5. **Blue/Green Deployment**
A Blue/Green Deployment strategy involves maintaining two identical environments, one referred to as "blue" (the production environment) and the other as "green" (the new version of the application). The new version is deployed in the green environment, thoroughly tested, and then traffic is switched from the blue to the green environment. This approach allows for instant rollbacks if any issues arise, ensuring minimal impact on users.

6. **Canary Deployment**
Canary Deployment is a strategy where a small subset of users or traffic is directed to the new version of the application, while the majority of traffic continues to use the previous version. This approach enables the monitoring of the new version's performance and detects any potential issues before fully rolling out the update. Canary deployments are particularly useful for large-scale applications that cater to a diverse user base.

7. **Shadow Deployment**
In a Shadow Deployment strategy, the new version of the application is deployed alongside the existing version, but the traffic is only directed to the existing version. The purpose of this strategy is to compare the behavior and performance of the new version with the existing one without affecting the user experience. Shadow deployments are valuable in assessing the impact of updates on the overall system performance before making them available to users.

8. **A/B Testing**
A/B Testing involves deploying multiple versions of an application and directing different subsets of users or traffic to each version. This strategy allows for a direct comparison of the performance and user experience between different versions. A/B testing is beneficial for making data-driven decisions about which version performs better based on user feedback and metrics.


### ***How are SOA, monolithic, and microservices architecture different?***


The monolithic, microservices architecture and service-oriented architecture (SOA) are quite different from one another. Here’s how:

* The **monolithic** architecture is like a large container where an application’s software components are assembled and properly packaged.

* The **microservices** architecture is a popular architectural style that structures applications as a group of small autonomous services modeled as per a business domain.

* The **SOA** is a group of services that can communicate with each other, and this typically involves either data passing or two or more services coordinating activities.


### ***Difference between Persistent Volume (PV) and Persistent Volume Claim (PVC)***
**Persistent volume (PV):**
A piece of storage in a Kubernetes cluster that's provisioned by an administrator or dynamically provisioned using Storage Classes. PVs are persistent, meaning they continue to exist even after the pods using them are destroyed. PVs can represent physical disks, file systems, or vendor-hosted storage resources. 

**Persistent volume claim (PVC):**
A request for storage by a user. PVCs are similar to vouchers that can be redeemed for storage access. PVCs specify which StorageClass the pod requires, and the master plane automatically finds a matching PV and binds the two. 

#### Here are some other things to know about PVs and PVCs:
* **StorageClass:** Administrators can define StorageClasses that indicate properties of storage devices, such as performance, service levels, and back-end policies. 
* **Dynamic provisioning:** You can define a storage class to leverage dynamic provisioning of persistent volumes so you won't have to create them manually. 
* **Data retention:** PVs ensure data retention regardless of a Pod's lifecycle. 
* **Storage management:** PVCs simplify storage management for developers. 
* **Stateful applications:** PVs are suitable for database storage where the database is not part of a stateful application
