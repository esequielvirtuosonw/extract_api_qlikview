# EXTRACT BI-API NEOWAY - QLIKVIEW

## Objective

Extract data of BI-API Neoway.

## Requirements

You have to install Qlikview Personal Edition and Qlik REST Connector to execute this project.
We leave the installers of these two programs in this project. They are on programs folder of this project.

Check the instalations guide in this two links.
> [QlikView](#http://go.qlikview.com/rs/qliktech/images/Downloading_and_Starting_the_QlikView_Desktop_Installation.pdf)

> [Qlik REST Connector](#https://help.qlik.com/en-US/connectors/Subsystems/REST_connector_help/Content/Install-QV-REST-connector.htm)

## Configurations

You have to change some configurations in the project to make it work.

1 - Adjustments on that configurations archives;

2 - Create variables to the fields of the tables, in the cases of insert data in postgreSql;

3 - Rename the data extraction and mapping files;

4 - Configure bat file.

> Most Important! Steps 2, 3 and 4 are usually provided by neoway after service delivery.

### ./config/config_client.qvs

In the API services delivery document, the access credentials (application and secret) are entered.

These credentials will be used in the first two variables of this document.

`Let application = 'yourAplicationName';
Let secret = 'yourSecretWord';`

The next step are define the form of storage data. This project offer three posibilities of storage (files csv, qvd and insert data on PostgreSql). The typeStore variable is responsible for this.

Example : `Let typeStore = 'INSERT_PG';`

If you choose to enter data in PostgreSql, you must enter the name of your ODBC connection in the dataBase variable.

Example : `Let dataBase = 'yourODBCConnectionName';`

Now, if you choose to do data storage in csv or qvd, the output files will be in the files folder of project.

## Run Extract

### Execute QVW

By executing in qvw file, open qlikview personal edition and run the extract using the command Ctrl+R.

> Most Important! QlikView Personal Edition has limitations for unlicensed use.
Running the qvw file created by the user who created the file does not have any problems, but if the file is opened by a user who did not create the file, it will only have 3 permissions to open this file before these attempts are blocked regardless of the attempt in other .qvw files.

### Schedule

For Windows, use start.bat through task manager.