### HOW DOES IT WORK ?
The script below goes through each ad group and finds the best ad. Then, it works out what could have happened if the other ads had been paused and all their impressions had gone to the winning ad. That tells you how much you’re missing out on (and which ad groups should be priorities when setting up new tests).

To do this, the script assumes the same number of total impressions for the ad group, but with the average performance — CTR, CPC and so on — of the winning ad (or ads, if there’s a tie).

Obviously, these are just simple assumptions. Realistically, the performance would vary because those impressions may have been of different quality (and even the number of impressions could have been different, because this ad/keyword combination could have a higher Quality Score and be eligible for more searches). However, it’s enough to give you a rough estimate.

You get to choose which metric makes an ad a winner — CTR is an obvious choice, but if you have enough converting traffic, then you can use conversions per impression, or value per impression, or something entirely different.

Note that there’s no statistical significance checking in the script — it just checks against click and impression thresholds — so if there are ad groups where the performance is close, you may want to check for yourself whether the winner really is the winner.

Oh, and the script looks at mobile-preferred ads separately from all device ads. After all, the mobile-preferred ads should be picking up all of the mobile traffic. If we treated mobile ads like regular ones, it would be inaccurate, as mobile traffic tends to be very different from desktop and tablet traffic.

### HOW DO I USE IT ?
To try this out for yourself, make a blank Google Sheet and take note of the URL. Then copy the script below, paste it into a new script in your account and change a few settings at the top:

1. Put your blank spreadsheet’s URL into spreadsheetUrl. This is where the results will go.
2. If you only want to look at ads in a few campaigns, you can enter phrases contained in campaign names which you would like to include in campaignNameContains. Or, if there are campaigns you don’t want to look at, you can list phrases contained in campaign names which you would like to exclude in campaignNameDoesNotContain. Or leave these both as [] to look at your whole account.
3. If ignorePausedCampaigns is true, then the script will only look at currently active campaigns. Set them to false if you want to look at currently paused campaigns as well as the active ones.
4. Similarly, if ignorePausedAdGroups is true, then the script will only look at currently active ad groups, and if it’s false, then paused groups will be included.
5. conversionMetrics lists which conversion metrics will appear in the spreadsheet. Your options for this are “ConvertedClicks,” “Conversions” and “ConversionValue” — you can pick of many of these as you like.
6. You have to pick which metric is used to determine the winning ad. Put that metric’s name in winningMetricName — this is used to name columns in the spreadsheet.
7. The winning metric is calculated by dividing one metric (winningMetricMultiplier) by another (winningMetricDivisor). For example, if the winning metric is CTR, the winningMetricMultiplier is “Clicks,” and the winningMetricDivisor is “Impressions.”
 * The script assumes the the largest winning metric is the best. You want the highest CTR or the highest conversion per impression.
8. impressionThreshold and clickThreshold are the minimum number of impressions and clicks ads need to be considered.
9. The script will look at the performance of the ads over a time period specified by dateRange.
	* You can use predefined date ranges like “LAST_30_DAYS,” “LAST_MONTH” or “THIS_MONTH.”
	* Or you can make your own with the format “yyyymmdd, yyyymmdd” — the first date is the start and the second is the end. For example “20160101, 20160630” would cover the 1st of January to the 30th of June 2016.
10. currencySymbol will be stuck in front of any currency values (i.e., costs and conversion values) in the spreadsheet.

#### Some notes:
* Only enabled ads that aren’t disapproved are considered.
* Ad groups where all ads are tied with the same winning metric are ignored. For example if all winning metric values are 0, the ad group will be ignored.
* The totals shown will not be the same as your account’s totals. This only reports the performance of ad groups with winning and non-winning ads.
* If the winningMetricMultiplier or winningMetricDivisor are not already one of the reported metrics, they will also be reported on. For example, if conversionMetrics was “Conversions,” but the winningMetricMultiplier was “ConversionValue,” then both conversions and conversion value would be reported in the spreadsheet.