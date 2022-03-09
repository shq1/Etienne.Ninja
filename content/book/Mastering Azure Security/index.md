---
title: "Mastering Azure Security"
tags: ["Sécurité 201"]
date: 2022-03-07T12:20:27-05:00
Note: 8/10
Auteur: Mustafa Toroman
image: cover.jpg
---


 
two different network  architectures in Azure datacenters – Default LAN Architecture (DLA) and Quantum 10 Architecture (Q10)

*****

Each cluster contains around 1,000 VMs. All VMs are managed by  the FabricController (FC).

*****

Establishment of policies, and continuous monitoring of their proper implementation, by the members of the governing body of an organization.

*****

If you want to make sure that all environments will strictly adhere to your rules, automatic deployments are your way to go. With a robust governance plan with policies and role-based access controls (RBAC), and by using deployments from a DevOps pipeline, such as Azure DevOps, you can make sure that your deployments and the target environment will be consistent.

*****

If you then make sure that changes to your environment can only be done from your DevOps pipeline tool, but never manually from the Azure portal, you are on your way to protecting your environments from inadvertent changes. You can use PowerShell for imperative deployments or Azure Resource Manager (ARM) templates, and Terraform for declarative deployments

*****

Every Azure subscription is tied to exactly one Azure Active Directory tenant (of which you ideally also only have one!).

*****

There are two different types of lock in Azure:
Delete locks ensure that no one can delete resources from your Azure subscription, by accident or on purpose. Authorized users can still read and modify a resource, but they can no longer delete it.
ReadOnly locks make sure that only authorized users are able to read a resource, but also that they cannot modify it nor delete it.

*****

You can only create or delete management locks when you have access to the Microsoft.Authorization/* or Microsoft.Authorization/locks/* management actions

*****

you can create a management group that contains all your production subscriptions and then apply a policy to the management group that limits resource creation to only those regions

*****

No one is given default access to the tenant root group. Only Azure AD global administrators have the right to elevate themselves to gain access and to make changes if necessary.

*****

You might want to give your security administrators read access to all resources that are created within the scope of your Azure AD tenant as they need to see all your subscriptions and management groups. Alternatively, you want to give application access to all your Azure subscriptions; for example, the ability to automatically deploy resources or to gather information about billin

*****

Azure Policy

*****

New resources are prevented from being created if they are non-compliant and existing resources can be brought into compliance if needed

*****

you might need to create a custom policy definition or use one of the built-in policy definitions that already come with Azure

*****

Parameters in a policy definition help to reduce the number of policy definitions

*****

assign it to a specific scope for the policy to take effect. This is what Microsoft calls a policy assignment

*****

Initiatives are collections of several rules that belong together.

*****

You can do so by defining audit policies instead of starting with a deny policy. With the audit effect, you can get a feeling for the impact your policy definition will make

*****

It is a good idea to create initiative definitions, even if you only want to create a single policy definitio

*****

A blueprint, in this case, is a repeatable template that you define once and then use during the creation of all your Azure subscriptions in the future

*****

With Azure Blueprints, you can declaratively deploy Azure resources and artifacts to all your subscriptions, such as the following:
Role assignments
Policy assignments
ARM templates
Resource groups
Locks

*****

No matter what it is, as soon as you want to automate complex deployments of standardized Azure environments, Azure Blueprints is your service of choice!

*****

For example, there are blueprint definitions that assign policies that are necessary to address specific NIST SP 800-53 R4 or ISO 27001 controls

*****

But for Log Analytics, it makes sense to deploy a separate workspace to every Azure region, so as to avoid being charged for cross-region network traffic

*****

Azure Resource Graph as a large index database for all your resources that can be queried using Kusto Query Language (KQL).

*****

This new approach is "identity is the new perimeter."

*****

Leveraging PowerShell, an attacker can easily:
Find out what security policy is in place
List all user accounts
Lock all user accounts by trying to log in with incorrect passwords
Repeat this script every x number of minutes.

*****

you could associate three security keys, one smartphone app, and a phone number with one account to make sure that there will always be at least one method you can use to fulfill an MFA challenge.

*****

With custom controls, you can redirect your users during the authentication process to an external compatible service to satisfy further authentication requirements outside of Azure AD

*****

Conditional Access policies consist of assignments and access controls. Assignments define who will be impacted by this Conditional Access policy and in which situation. Access controls define whether access is blocked or granted, and if it's granted, on which conditions.

*****

When selecting all users and then blocking access with this policy, this will also affect all your administrator accounts. That said, you could lock yourself out when activating this policy. It is recommended to apply a policy to a small set of users first to make sure it behaves as expected!

*****

A risky sign-in indicates a sign-in attempt that might have been performed by an attacker and not the legitimate account owner

*****

The difference from a sign-in risk policy is that you can either block access or enforce a password change for a risky user.

*****

Password Hash Sync + Seamless SSO is the easiest way to go. With this, your on-premises password hashes are replicated to the corresponding cloud identities, so users can use the same usernames and passwords across all login environments.

*****

Pass-through Auth + Seamless SSO. In this scenario, you install a software agent on one or more on-premises servers. These servers can validate your user credentials directly against your on-premises domain controllers

*****

Federation with Active Directory Federation Services (AD FS) or another federation service is the most complex authentication method. It should be used in scenarios where sign-in features are not natively supported by Azure AD

*****

We recommend always enabling password hash synchronization in Azure AD Connect. Doing so, you have a fallback scenario in case your on-premises authentication platform is not working properly, and you can use Azure AD Identity Protection to get leaked credential reports. Furthermore, you can enable self-service password reset (SSPR) when password hash synchronization is enabled.

*****

the new password is written back to the on-premises Active Directory. The feature you need to enable in Azure AD Connect in this case is called password writeback.

*****

AD Premium P2 license:
Azure AD PIM
Azure AD Identity Protection
Risk-based Conditional Access policies

*****

Azure AD Premium P1 license is sufficient:
Azure MFA
Conditional Access based on group, location, and device status
Self-service password reset

*****

Each VNet that we create is a completely isolated piece of network in Azure. We can create multiple VNets inside one subscription,

*****

VNets that have overlapping IP ranges will not be compatible for connection.

*****

network security group (NSG) to control traffic for Azure VMs. NSGs can be used to control inbound and outbound traffic.

*****

The default inbound rules will allow any traffic coming from within a VNet and any traffic forwarded from Azure Load Balancer. All other traffic will be blocked.

*****

Conversely, the default outbound rule will allow almost any outbound traffic

*****

An NSG associated on a subnet level will have all the rules applied to all the devices associated with that subnet

*****

For example, if we create a rule to allow traffic over port 443 with a priority of 100, and create a rule to deny traffic over port 443 with a priority of 400, traffic will be allowed, as the allow rule has a greater priority.

*****

It's much better to have VMs that have similar requirements associated on a subnet level.

*****

The first one would be to create an S2S between the VNets

*****

Another option would be to create VNet peering. An S2S connection is secure and encrypted, but it passes over the internet. Peering uses an Azure backbone network in order to route traffic, and it never leaves Azure.

*****

VNet service endpoints enable us to extend some Platform as a Service (PaaS) services to use private address spaces.

*****

Network Virtual Appliance (NVA) can be used. An NVA can be deployed from Azure Marketplace. Once deployed, you will realize that an NVA, in fact, is an Azure VM with a third-party firewall installed. Most industry leaders are present in Azure Marketplace and we can deploy firewall solutions that we are used to in an on-premises environment. It's important to mention that we don't have to decide between NSGs or NVAs; these can be combined for additional security.

*****

Azure Application Gateway is an L-7 load balancer and we could question the security aspects of it (if we exclude SSL/TSL termination), as it's more a question of reliability and availability

*****

Application Gateway has an amazing security feature called Azure Web Application Firewall (WAF). WAF protects web applications against common exploits and vulnerabilities.

*****

Application Gateway works with services in a single region where Azure Front Door allows us to define, manage, and monitor routing on a global level