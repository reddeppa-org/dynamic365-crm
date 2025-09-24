
# Dynamics 365 Sales samples

This folder contains samples for Dynamics 365 Sales app, a first-party model-driven app built by Microsoft. More information: [Dynamics 365 Sales documentation](https://docs.microsoft.com/dynamics365/sales-enterprise/help-hub)

The samples also work for [Dynamics 365 Customer Engagement (on-premises), version 9](https://docs.microsoft.com/dynamics365/customerengagement/on-premises/overview).

# How to run samples?

1. Download or clone the repo so that you have a local copy.
1. (Optional) Edit the cds/App.config file to define a connection string specifying the Common Data service instance you want to connect to.
2. Open the sample solution in Visual Studio and press F5 to run the sample.
    - If you have specified a connection string in cds/App.config, any sample you run will use that connection information.
    - If you haven't specified a connection string in cds/App.config file, a dialog ([XRM tooling common login control](https://docs.microsoft.com/powerapps/developer/common-data-service/xrm-tooling/use-xrm-tooling-common-login-control-client-applications)) will open each time you run the sample and you will need to enter information about which Common Data Service environment you want to connect to and the credentials you want to use. This dialog will cache previous connections so that you can choose a previously used connection. See the **Known issue** and its workaround later for this scenario.

The samples in this repo that require a connection to a Common Data Service environment to run will include a linked reference to the cds/App.config file.
    
## Known issue 

With the recent changes to .NET Framework, an exception is thrown when a sample tries to open the XRM tooling common login control dialog. As a workaround for the time being, do one of the following:
- Specify a connection string in cds/App.config to run the samples.
- Enable **HTTP Activation** on your computer where you are running the samples, and then run the sample without specifying a connection string in cds/App.config.
    
    ![](media/http-activation.png "Enable HTTP Activation")
    
This issue will be resolved in a future update when we distribute the updated assemblies through our [NuGet package](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.WpfControls/). 
