
The script goes through your account’s search terms and adds up the performance of all queries containing your phrases at the account, campaign and ad group level. This is recorded in a Google spreadsheet for you to peruse. There’s also a sheet with the overall stats for each phrase by month, which shows you how seasonality affects the queries.

### HOW DO I USE IT?

To use the script, you need to make a blank Google spreadsheet (for the report) and make a note of its URL. Then, copy the code below into your account, and change a few options at the top:

1. startDate and endDate determine the date range of the data. Enter them in yyyy-mm-dd format.
2. currencySymbol is used when formatting cost data in the report.
3. campaignNameContains and campaignNameDoesNotContain filter which campaigns the script gets data from. For example, if campaignNameContains is [“Brand”, “Generic”] then only campaigns with names containing “brand” or “generic” are included. If campaignNameDoesNotContain is [“Display”, “Competitor”] then any campaigns with names containing “display” or “competitor” are ignored.

 * This is not case-sensitive.
 * Leave blank, [], to include all campaigns.
 * If you need to put a double quote into campaignNameContains or campaignNameDoesNotContain, put a backslash before it.

4. ignorePausedCampaigns should be set to true if you only want to look at currently active campaigns, or false if you want to include them.

5. Similarly, ignorePausedAdGroups should be true to only look at currently active ad groups, and false to include paused ones.
6. spreadsheetUrl is the URL of a Google Doc spreadsheet, which the results will be copied into. Create a blank spreadsheet and put the URL in here.
7. adjectives is the list of words and phrases to be reported on. Put them in double quotes, separated by commas: [“fitter”, “happier”, “more productive”]
 * Note that this should match what you would expect to find in the search query — for example, don’t use punctuation that won’t be shown in the report.
8. If clearSpreadsheet is true, any data already in the spreadsheet will be overwritten. If it’s false, then the script’s results will be added at the end of the sheets.
 * The exception is the Monthly Data sheet, which will always be replaced.
9. Set lookAtCompletePhrases to true if you only want to see how your phrases behave when they are whole words on their own.
 * For example, if one of your adjectives was “super”, queries like “new super shoes” will always be included. But “superman shoes” would only be included if lookAtCompletePhrases were false, because “super” appears within a word rather than as a whole word on its own.

There are also some advanced options: thresholds for the different statistics are given so that you can stop the report showing ad group- or campaign-level performance where an adjective had very few searches.
