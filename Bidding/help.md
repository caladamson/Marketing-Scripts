Before running it, you first need to make sure you’ve got the correct settings. There are a few things to configure:

1. The bid multipliers run from a Google spreadsheet and the URL needs to be inserted into the code as spreadsheetUrl. We suggest you copy our template sheet and set your bids up in it. The doc should look something like this: In cells B2 to H25, input the bid multipliers: a 0% bid multiplier doesn’t change any bids, and a 25%/-25%

2. If you want to use mobile multipliers as well, they go in the second sheet of the same spreadsheet.

3. You need to set the variable shoppingCampaigns to true if you want to use it on shopping campaigns, or to false to use it on Search or Display campaigns.

4. Set runMobileBids to true if you want to change your mobile bid adjustments every hour, or set it to false if you only want to change the ad schedules.

5. If you only want to use these multipliers on some campaigns, use excludeCampaignNameContains and includeCampaignNameContains to say what should or shouldn’t be in the campaign names.
You then need to set up a schedule so the script runs hourly. The script doesn’t set all schedules up in advance, because AdWords won’t allow enough bidding windows – instead it will continually update the ad schedules, so the next few hours are always filled in. Any times after more than a few hours away will be filled with a 0% modifier, as a safety feature.

And now all that’s left to do is sit back and see overall conversion rates rocket!