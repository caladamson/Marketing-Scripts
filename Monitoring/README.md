

The script checks each campaign’s spend and budget. All you need to do is set a multiplier threshold — if the spend is larger than the budget multiplied by the threshold, then the campaign is labeled. You’ll get an email listing the newly labeled campaigns, along with their spend and budgets. And if you want, you can set another threshold so that if the spend gets too far over your budget, the campaign will be paused.

The script also checks if the campaign’s spend is under your labeling and pausing thresholds, so it can unlabel and unpause them. That means that when it’s a new day and nothing has been spent yet, the labels will be removed, and anything the script has paused will be reactivated. It also means that if a campaign is over budget, but you increase its budget, the labeling and status will reflect the new, increased budget.

### HOW DO I USE IT
1. campaignNameContains and campaignNameDoesNotContain filter which campaigns the script will look at. For example, if campaignNameContains is [“Generic”, “Competitor”] then only campaigns with names containing “generic” or “competitor” will be labeled or paused. If campaignNameDoesNotContain is [“Brand”, “Key Terms”] then any campaigns containing “brand” or “key terms” in the name will be ignored (and can overspend as they like).

* This is not case-sensitive.
* Leave blank, [], to include all campaigns.
* If you need to put a double quote into campaignNameContains or campaignNameDoesNotContain, put a backslash before it.

2. email is a list of addresses that will be emailed when campaigns are labelled or paused.
Note that emails will be sent even when the script is being previewed and not making changes.

3. currencySymbol, thousandsSeparator and decimalMark are used to format the budget and spend numbers in the email.
4. labelThreshold determines how much the campaign must spend, compared to its budget, for the script to label it as overspending.
 * For example, if you set labelThreshold to 1, then campaigns will be labeled and you will be emailed if the spend is equal to the budget. If you set it to 1.2, then the campaign is labeled and email sent if spend is 120 percent of the budget.
 * 
5. labelName is the name of the label that will be applied to overspending campaigns.
6. Set campaignPauser to true if you want campaigns too far over their budgets to be paused. Set it to false if you do not want the script to pause campaigns, no matter how much they spend (the script will still label and email you according to the labelThreshold).

7. pauseThreshold determines how much the campaign must spend, compared to its budget, for the script to pause it (if campaignPauser is true).
* This works the same as labelThreshold: If it is 1.2, then campaigns will be paused if their spend is 120 percent of the budget.
* This must be greater than or equal to the labelThreshold. The script needs the paused campaigns to be labeled so it knows which to reactivate when their spend becomes lower.

Preview the script to make sure it’s working as expected (and check the logs in case there are any warnings). Then set up a schedule so the script runs hourly.

### A few things to note:
* The script only works with search and display campaigns. It can’t help with video, shopping or universal app campaigns.
* This script can’t completely prevent your going over budget. The script only runs hourly, so the campaign can go over the spend threshold between runs. And there’s a 15- to 20-minute lag in the spend data.
* Scheduled scripts don’t run on the hour, so campaigns will not be reactivated as soon as a new day begins. Instead, they’ll be reactivated when the script first runs on the new day, sometime between midnight and 1:00 a.m. Most campaigns receive little traffic at this time anyway — but if that’s not the case for you, you might want to set up automated rules to unpause things exactly as midnight strikes.
* You can set labelThreshold to be less than 1. For example, if you set it as 0.9, you’ll get an email when the campaign reaches 90 percent of its budget.
