# Developing--Testing--and-Publishing-an-Azure-Function-from-CLI
20487C_MOD05_DEMO_L4


### Developing, Testing, and Publishing an Azure Function from CLI

1. Open the Azure Portal.

2. If a page appears asking for your email address, enter your email address, and then click **Continue**. Wait for the sign-in page to appear, enter your email address and password, and then click **Sign In**.

   >**Note**: During the sign-in process, if a page appears asking you to choose from a list of previously used accounts, select the account that you previously used, and then continue to provide your credentials.

3. If the **Windows Azure Tour** dialog box appears, to close it, click **X**.

4. In the navigation blade, click **Create a resource**. 

5. In the **New** window, select **Compute**, and then select **Function App**.

6. In the **Function App** blade, in the **App name** box, enter a globally unique name.

   >**Note**: Save the App name in any code editor. You will need it when publishing a new **Azure Function** to **Azure**.

7. From the **Location** list, select the region that is closest to your location.

8. Set **Application Insights** to **Off**.

9. Click **Create**. Wait for the Microsoft Azure Functions app to be created.

10. Open the Command Prompt window.

11. To change the directory, at the command prompt, paste the following command, and then press Enter:

    ```bash
        cd [RepositoryRoot]\AllFiles\Mod05\DemoFiles\AzureFunctions
    ```

12. To create a local Functions project, paste the following command:

    ```bash
        func init MyAzureFunctionProj -n --worker-runtime dotnet
    ```

13. To change the directory to the new Functions project folder, paste the following command, and then press Enter:

    ```bash
        cd MyAzureFunctionProj
    ```

14. To create a new Azure function for your new Functions project, paste the following command, and then press Enter:

    ```bash
        func new --language C# --template "HttpTrigger" --name MyAzureFunc
    ```

15. To test the new Azure function locally, paste the following command, and then press Enter:

    ```bash
        func host start --build
    ```

    > **Note**: If windows Security Alert dialog box appears click **Allow access**.

16. Open a browser and navigate to **http://localhost:7071/api/MyAzureFunc**.

17. Add the following query string value to the end of this URL, and then press Enter to execute the request:

    ```cs
        ?name=<yourname>
    ```

    >**Note**: Replace *<yourname>* variable with your actual name.

18. Check that you are getting the expected response such as the following:

    ```cs
         "Hello {Your Name}"
    ```

      >**Note**: This is the response from Microsoft Edge. Other browsers may include displayed XML.       

19. To sign in to Azure with your credentials before publishing the new Azure function to Azure, paste the following command, and then press Enter:

    ```bash
        az login
    ```

    >**Note**: You will get the following message: **To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code** *{some code}* **to authenticate**. Follow the instructions to sign in with your username and password.

20. To publish your new Azure function to Azure, paste the following command, and then press Enter:

    ```bash
        func azure functionapp publish {Your App name}
    ```

    >**Note**: Replace *{Your App name}* with your actual app name that you noted in step 6.

21. Go back to azure portal and open the azure function, click on **Manage** then under **Function keys**, click on **Click to show** and copy the **default key** value.

22. Open a browser and navigate to **https://{Your App name}.azurewebsites.net/api/MyAzureFunc?name={Your Name}&&code={YourFunctionKey}**.

    >**Note**: Replace *{Your App name}* with your actual app name and replace *{Your Name}* with your actual name.

23. Check that you are getting the expected response such as the following:

    ```cs
         "Hello {Your Name}"
    ```

      >**Note**: This is the response from Microsoft Edge. Other browsers may include displayed XML.  


​     
