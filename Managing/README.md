### HOW DOES IT WORK ?
The script reads a Google spreadsheet that you’ve created and matches that against your campaigns’ queries. If there’s a query that doesn’t match one of your keywords, a negative keyword will be added to exclude the query.

The script chops the query into bits and makes phrase match negatives wherever possible, so each negative can exclude as many unwanted searches as possible while keeping anything that matches the keywords. It’s a bit of a hack, but if you read on, you’ll see the results are worth it.

Using this script, you could run one campaign just for your key search terms. But it also means that you can run your Shopping campaigns like the best Search ones — with separate Broad and Exact campaigns. The Exact campaigns will bring in your “business as usual” traffic, and your Broad ones bring in the less predictable long-tail queries.

The beauty of using scripts is that you can get a lot more granular than that with no limit on scale. The Exact campaign contains ad groups, each of which has its own set of keywords that you can define in a spreadsheet. So you can match specific keywords to bids and products. This is a really handy feature — the ability to decide the product range that you want to show for specific generic queries.

### HOW DO I USE IT?
1. Write your exact match keywords into a Google Spreadsheet, with their campaign and ad group. Note that there are no “close variants” here — the script will exclude searches that are as much as a letter off. Also note that the script ignores capitalization and treats all punctuation (aside from ampersands) as a space, so “Spider-man’s” is the same as “spider man s” here.
2. Set your Broad shopping campaign to High priority.
3. Copy all of your keywords from your spreadsheet and add them as exact negatives.

4. Set your Exact shopping campaign to Low priority, so it only picks up queries that can’t be taken by the Broad campaign.
5. Copy the script and paste it into your account. At the top of the script, you need to change spreadsheetUrl to the URL of the Google Doc spreadsheet with the keywords in it.
6. Before running the script for the first time, click “Preview” — the script will run but won’t actually make changes, so you can see what negatives the script is going to add. If there are any problems, then there will be messages in the Logs.
7. When it looks like everything is fine, click “Run script now” so the script will run for real and actually add negatives. Then, schedule the script to run daily — that means it can keep reading your new queries and adding new negatives.

If you want to add new Exact keywords later:

* Write the keyword, with its campaign and ad group, at the end of the spreadsheet.
* Add the keyword as an exact match negative to the Broad campaign.
* Look at the keyword’s ad group in the Exact campaign, and remove any negative keywords that would exclude the keyword.


Because the script checks search queries daily, it can add negatives for anything required. You don’t have to worry about changing the Exact campaign’s negatives if you’re adding negatives to the Broad campaign, and you don’t have to worry about letting in the wrong queries if you take negatives out of the Exact campaign — the script will fill in the necessary negatives once they appear in the SQR.

If you want to split up your budget, you can have multiple Exact campaigns; because you’re funneling queries with the script’s negatives, you can have multiple campaigns at the same priority.
