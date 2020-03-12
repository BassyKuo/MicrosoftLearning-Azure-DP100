# Tips

The labs in this repo have been tested using a variety of operating systems, web browsers, Azure subscription types, and Azure regions. However, we can't test every possible configuration. This document details some of the issues we've seen students experience, and workarounds that have helped.

## I can't connect to a portal or web interface in the labs

- **Problem**: You get an error when trying to connect to a link in the labs or from one portal to another.
- **Possible Cause**: You may be using a firewall that restricts the sites you can access.
- **Possible Solution**: Speak to your network administrator or consult your personal firewall documentation to enable access to the required sites. Alternatively, if you are taking this course through an authorized learning partner, you may be provided with a hosted lab environment that consists of a Windows 10 virtual machine with a browser installed - if so, try to access this "jump box" using a web browser, and then use the browser-based virtual machine to perform the labs.

## I'm unable to create an Azure Machine Learning workspace in Azure

- **Problem**: You experience an error when trying to create an Azure Machine Learning resource in your Azure subscription.
- **Possible Cause**: If you are using a subscription provided by your employer or school, you may not have permission to create a machine learning resource.
- **Possible Solution**: Ask your subscription administrator to grant you the required permissions, or create your own Azure subscription at [https://azure.microsoft.com](https://azure.microsoft.com). If you are taking this course through an authorized learning partner, you may be provided with an *Azure Pass* that will provide a temporary subscription for the course - if so, use it.

## Azure signs me in automatically with the wrong account

- **Problem**: When you open the Azure portal in youtr browser, you don't get prompted to sign in - instead you are signed in automatically with a different account from the one you want to use in the labs, or you get an authentication or "access forbidden" error.
- **Possible Cause**: If you use multiple Microsoft accounts (for example, a work account and a personal outlook.com account) on the same computer, your browser may cache credentials and sign you in automatically without giving you the opportunity to select a different account.
- **Possible Solution**: Try signing out of all Microsoft accounts in all browser sessions and clear the browser cache, or opening a *private browsing* session in your browser and use that to complete the labs. Alternatively, install a second browser and use that. If you are connecting a compute instance, try restarting the compute instance. If you are taking this course through an authorized learning partner, you may be provided with a hosted lab environment that consists of a Windows 10 virtual machine with a browser installed - if so, use it.

## Azure Machine Learning studio stops responding

- **Problem**: While working in Azure Machine Learning studio, the user interface becomes unresponsive.
- **Possible Cause**: Azure Machine Learning may sign you out automatically after a period of time.
- **Possible Solution**: Refreshing the page usually forces you to reauthenticate, and re-establishes your session.

## I see a *service error* when connecting to Jupyter notebook

- **Problem**: While working in a Jupyter notebook, a *service error* message is displayed.
- **Possible Cause**: The Jupyter service in the compute instance may have stopped reponding.
- **Possible Solution**: Restart the compute instance. If it won't restart, create a new one (and reinstall the Azure ML SDK in the Jupyter terminal after starting it).

## I see a *kernel error* in a Jupyter notebook

- **Problem**: While working in a Jupyter notebook, a *kernel error* message is displayed and you can't save the notebook.
- **Possible Cause**: Jupyter may sign you out automatically after a period of time.
- **Possible Solution**: Switch to the browser tab containing the Jupyter home page, and refresh it. This forces you to reauthenticate, and re-establishes your session.

## The terminal in Jupyter is blank

- **Problem**: Opening a new terminal in Jupyter just displays a black screen.
- **Possible Cause**: There may be issues with some browsers.
- **Possible Solution**: Click in the black screen and press ENTER - this may force the screen to refresh and display the terminal prompt. If that doesn't work, try installing a second browser and use that, or if you are taking this course through an authorized learning partner, you may be provided with a hosted lab environment that consists of a Windows 10 virtual machine with a browser installed - if so, use it.

## Visual Studio Online doesn't open

- **Problem**: Opening Visual Studio Online doesn't display the Visual Studio interface.
- **Possible Cause**: There may be issues with some browsers.
- **Possible Solution**: Install a second browser and use that. If you are taking this course through an authorized learning partner, you may be provided with a hosted lab environment that consists of a Windows 10 virtual machine with a browser installed - if so, use it.

## I get unexpected Python package errors when running code

- **Problem**: Code doesn't run as expected, but results in an error indicating an issue with Python packages.
- **Possible Cause**: There are frequent updates to the Azure Machine Learning Python SDK, and it depends on numerous other Python packages. It's possible that the required version of a Python package is not installed.
- **Possible Solution**: Try using the following command to force a reinstall of Azure Machine Learning SDK components and dependencies.

    ```bash
    pip install --upgrade --force-reinstall azureml-sdk[notebooks,automl,explain]
    ```

## I get time-outs or spurious errors when using Azure Machine Learning

- **Problem**: Unexpected time-outs or other errors occur.
- **Possible Cause**: Azure Machine Learning is a cloud service, and as such it is dependent on other network services. Additionally, many features in Azure Machine Learning are currently in preview. Complete outages are rare, but intermittant errors can occur. There may be a transient issue with the service or network.
- **Possible Solution**: If something doesn't work, and you've tried everything you can think of; try leaving it for a while and try again later. You can check for Azure status at [https://status.azure.com/en-us/status](https://status.azure.com/en-us/status), and you can check for recent issues in the Azure ML SDK at [https://social.msdn.microsoft.com/Forums/home?forum=AzureMachineLearningService](https://social.msdn.microsoft.com/Forums/home?forum=AzureMachineLearningService).
