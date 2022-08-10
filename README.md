# Qlik Azure Cost Explorer 

![Screenshot](img/screenshot.png?raw=true "Screenshot")

## License Summary

This project is made available under a modified MIT license. See the [LICENSE](LICENSE) file.

## Disclaimer

1. This is **not** a Qlik Supported Project/Product.
2. Contributions such as Issues, Pull Request and additional codes are welcomed.
3. **Qlik Inc.** or **Qlik Support** has no affiliation with this project. The initial version was developed by [Clever Anjos](https://www.linkedin.com/in/cleveranjos/) who is currently employed as Principal Solution Architect at Qlik Partner Engineering Team.

## Purpose

The purpose of this script is use the [Azure Billing REST API](https://docs.microsoft.com/en-us/rest/api/billing/) endpoint to retrieve cost data about one (or more) Azure subscriptions.

This is a 100% Qlik Sense app that can be used both on SaaS or in a on-premise environment

## Installation / Configuration

### Downloading the app

1. Open this [link](qvf/Azure%20Cost%20Explorer%20-%20Github.qvf)
2. Click on the button "Download" on your right side
3. Save the file on your computer
4. Import your application in your Qlik Sense instance (on-premise or SaaS)

### Importing your application

Please follow the procedures below if you are not familiar with importing Qlik Sense apps to your environment.

[Importing Qlik Sense Apps on-premise](https://help.qlik.com/en-US/sense-admin/May2022/Subsystems/DeployAdministerQSE/Content/Sense_DeployAdminister/QSEoW/Administer_QSEoW/Managing_QSEoW/import-apps.htm)

[Uploading apps to your Qlik Sense SaaS](https://help.qlik.com/en-US/cloud-services/Subsystems/Hub/Content/Sense_Hub/Apps/uploading-apps.htm)

### Getting your credentials

Please refer to this [blog post](https://www.inkoop.io/blog/how-to-get-azure-api-credentials/) and this [Azure documentation](https://www.inkoop.io/blog/how-to-get-azure-api-credentials/) as a tutorial to get your tenant_id, client_id and client_secret that will allow the Azure Cost Explorer to connect to [Azure Billing REST API](https://docs.microsoft.com/en-us/rest/api/billing/)

### Configuring your application

1. Open your Data Load Editor and open the section **"--Config"**
2. Set the first three variables with the values you created from the **"Getting your credentials"** section
3. Set the variable **DC_POST** with a POST REST connection name you might have on your environment. If you don´t have one, create a POST REST connection pointing to this [endpoint](https://postman-echo.com/post)
4. Set the variable **DC_GET** with a GET REST connection name you might have on your environment. If you don´t have one, create a GET REST connection pointing to this [endpoint](https://postman-echo.com/get?test=123)
5. Set the **DC_QVD** to a data connection name where the app would store the historical QVD´s
6. Set the variable **OVERWRITE** to "1" if you want the app to always overwrite any QVD or "0" if you want to keep any stored QVD
7. Set the variable **MONTHS** to a number indicating how many months you want to extract from the API. The app will load all previous QVD´s in the DC_QVD data connection

### Mapping your fields

We provide a simple way to map your fields values using a mapping function. To do that, adjust the "Mapping" section accordingly to your needs

### Customizing your app

Feel free to add more sheets or objects to this application. It is meant to be much more as a template than a final product

## Versions and Roadmap

* Aug 2022 - Initial version
* Q3 2022 - AutoML integration (Planned)

Feel free to suggest any improvements. We will evaluate and implement when your suggestion was accepted. Please use the [Feature Request](https://github.com/Qlik-PE/qlik-azure-cost-explorer/issues/new?assignees=&labels=&template=feature_request.md&title=)