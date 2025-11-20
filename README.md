# Xero-Custom_Reporting-Google_Sheets
Pull data from Xero to create custom reports in Google Sheets delivered by email using Google Apps Scripts

Overview
The following functions work together to automate the process of fetching financial reports from Xero, processing the data, and sending out the reports via email

Global Constants:
Stores important values like client ID, client secret, redirect URI, tenant ID, spreadsheet ID, and sheet name that the script uses.

onOpen:
Adds a custom menu to the Google Spreadsheet with options like 'Authorize', 'Refresh Access Token', 'Fetch Balance Sheet Report', 'Fetch Income Statement', and 'Email Reports'.

getOAuthService:
Sets up the OAuth2 service to handle authorization with the Xero API. This allows the script to securely access Xero data.

authCallback:
Handles the response after the user authorizes access to their Xero account. It confirms if the authorization was successful or denied.

authorize:
Initiates the authorization process. If access is not granted or has expired, it prompts the user to authorize again.

fetchBalanceSheetReport:
Retrieves the balance sheet report from Xero and writes it to the Google Sheet. It handles any errors that occur during this process.

sendErrorEmail:
Sends an email if an error occurs while fetching the balance sheet report, notifying the specified email address of the issue.

writeToSheet:
Writes the retrieved balance sheet data to the specified sheet in the Google Spreadsheet.

fetchProfitAndLossReport:
Retrieves the profit and loss report from Xero for different date ranges and writes the data to the appropriate sheets.

fetchAndWriteData:
Fetches the profit and loss report data from Xero and writes it to a specified sheet. It handles errors and logs any issues.

sendErrorEmail (repeated):
Sends an email if an error occurs while fetching the profit and loss report, notifying the specified email address of the issue.

writeToSheetPnL:
Writes the profit and loss data to the specified sheet in the Google Spreadsheet.

emailReports:
Collects various financial reports, converts them to PDFs, merges some of them, and sends the reports via email if certain conditions are met.

fetchPDFWithRetry:
Tries to fetch a PDF version of a sheet from the Google Spreadsheet, retrying multiple times if necessary.

mergePDFsUsingPDFApp:
Merges multiple PDF files into a single PDF using a custom PDF application.

PDFApp Class:
A custom class that loads necessary libraries and provides methods to merge PDF files.
