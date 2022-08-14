# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*

- Both Azure Vms and Azure App services allow you to host a Python web application. Azure VMs are an example of Infrastructure as a Service, while App Service is an example of Platform as a Service.

 Cost Analysis: Azure Virtual Machines are more expensive to run than App Service. The basic VM configuration cost around $3.8.mnth at the time of writing this document. App services, on the other hand, provide a free tier for deploying an application, albeit with limited features. As the current project requires only basic CRUD operations, the free tier app service will be suffice. A downfall of App service is that, unlike VM plans , we do not have a pay as you go option,so billing will be on the service plan even if you don't use the app

 Scalability: When it comes to scalability, Azure Vms offer all kinds of options from managing the configuration of the server, OS versions , updates,custom inages and full control over managerial aspects as well as the environment and hardware . The Azure App service limits certain aspects like OS selection,only supports Windows and Linux and is only suitable for a few supported coding languages. Although VMs are highly scalable , app services also provide options for both vertical and horizontal scaling by choosing different pricing tiers. But there is still a limit for app services to scale up. An app service can only support up to 14Gb of RAM and not more.

 Availability: Azure Vms and App services both ensure and provide high availability, with Vms supporting load balancing and different scale sets. App service, on the other hand, can support multi-region zones while ensuring failures are minimized and handled efficiently. As discussed before, the App Service supports both Windows and Linux OS , but lacks support for many programming languages apart from some of the most commonly used ones.

 Workflow: Azure Vms are basically a new server setup where the owner can choose from many configurations available . Creating Azure Vms requires a user to have an Azure subscription and the resource group to which its grouped.The process of setting up a VM is time-consuming as the user is required to configure the OS, and is responsible for all the development tools required , deployment, and publishing of an application. Once the VM is created, the user can start accessing it using either CMD/shell or RDP based on the OS installed. Deploying an app requires connecting to the Vm and setting up folders and IIS and connection. This is a complicated process when considering developing and deploying a basic or small-scale application.
 The app service, on the other hand, gives the developer all the time required to concentrate on development and testing as it provides the required platform and development tools. The user has to just deploy the codes and the app service makes the app available. Creating an app service also requires a subscription and also an app service plan, which will be billed regardless of the usage of the app installed. Users can choose from the region and available tiers.

- For this project 'cd1756' to create an Article CMs app, we are selecting the Azure app service

- Furthermore, the app service is a much simpler and straightforward approach, allowing us to focus on development and deployment. It also supports continuous deployment using Github and other repos. The  App service supports the Pyhton stack and provides a Linux OS for us to host the web app.


### Assess app changes that would change your decision.

If we plan to expand the scope of our application and to develop new modules and make the app highly available, and create a web api to support both the app and other new dependent applications, we will be able to choose a higher tier  and also select more features that help make the app available and maintainable properly. If the app in the future has to be expanded and managed for a large business, allowing testing and deployments to production as well as requiring changes in server configurations , we can opt to create a Vm using Azure Vms and move or migrate the app over to Vm.