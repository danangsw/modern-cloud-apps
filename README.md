# App modernization hands-on lab step-by-step

## Abstract and learning objectives

In this hands-on lab, you will implement the steps to modernize legacy on-premises applications and infrastructure by leveraging cloud services, while adding a mix of web and mobile services, all secured using Azure Active Directory.

At the end of this hands-on lab, you will be better able to build solutions for modernizing legacy on-premises applications and infrastructure using cloud services, and implement a mix of web and mobile services secured by Azure Active Directory.

## Overview

The App Modernization hands-on lab is an exercise that will challenge you to implement an end-to-end scenario using a supplied sample that is based on Microsoft Azure App Services and related services. The scenario will include implementing compute, storage, security, and search, using various components of Microsoft Azure. The hands-on lab can be implemented on your own, but it is highly recommended to pair up with other members at the lab to model a real-world experience and to allow each member to share their expertise for the overall solution.

## Solution architecture

After lawyers affirmed that Contoso, Ltd. could legally store customer data in the cloud, Contoso created a strategy that capitalized on the capabilities of Microsoft Azure. Below is a diagram of the solution architecture you will build in the lab. Please study this carefully, so you understand the whole of the solution as you are working on the various components.

The solution begins with mobile apps (built for Android and iOS using **Xamarin**) and a website, both of which provide access to PolicyConnect. The website, hosted in a **Web App**, provides the user interface for browser-based clients, whereas the Xamarin Forms-based apps provide the UI to mobile devices. Both mobile app and website rely on web services hosted in an **API App**. In addition to the API App, a light-weight, serverless API is provided by **Azure Functions Proxies** to provide access to policy documents stored in **Blob Storage**. **Azure API Management** is used as a proof of concept for the future goal to create an API Store for development teams and affiliated partners. Sensitive configuration data, like connection strings, are stored in **Key Vault** and accessed from the API App or Web App on demand so that these settings never live in their file system. Full-text search of policy documents is enabled by the Indexer for **Blob Storage** (which indexes text in the Word and PDF documents) and stores the results in an **Azure Search** index. **PowerApps** enable authorized business users to build mobile and web create, read, update, delete (CRUD) applications that interact with **SQL Database** and Azure Storage, while **Microsoft Flow** enables them to orchestrations between services such as Office 365 email and services for sending mobile notifications. These orchestrations can be used independently of PowerApps or invoked by PowerApps to provide additional logic. The solution uses user and application identities maintained in **Azure AD**.
