# NYT_FreeDailyXword
Play NYT crosswords for free (Desktop browsers only)

## How does this work?
The site [xwordinfo.com](https://www.xwordinfo.com/) contains hints, solutions and analysis of all NYT crosswords but *normally* only lets you [solve pre-Shortz (1942-02-15 to 1993-11-20) crosswords](https://www.xwordinfo.com/Calendar?type=pssolve). That's still plenty but if you want any more recent crosswords, you're supposed to go the official route and pay a subscription to NYT or NYT Games.

However, you can bypass restrictions of the (desktop only) interactive solver at XWord Info by making the site request a recent crossword even though the page believes you're solving an ancient (1000-year-old) one.

I might consider making this into a userscript or browser extension but currently, this method  does not require you to run any closed-source or questionable code in your browser.

## Install & use

1. Get [Redirector](https://github.com/einaregilsson/Redirector) for your browser
2. Download [Redirector_NYT_FreeDailyXword.json](https://raw.githubusercontent.com/ChaoticNeutralCzech/NYT_FreeDailyXword/main/Redirector_NYT_FreeDailyXword.json) from this repository (just right-click and "Save as...")
3. Open Redirector's settings and import Redirector_NYT_FreeDailyXword.json (existing redirects won't be overwritten)
4. Go to https://www.xwordinfo.com/Solve?date=12/31/2023 (with the current date, or use the "Select a different puzzle" button to pick any date)

## Limitations & workarounds

1. The "Previous" & "Next" buttons don't work.
    - Use the calendar or manual date entry in the URL.
2. The "Solution and commentary" button results in "No valid puzzle found for xx/xx/10xx"
    - Change "10xx" to "20xx" in the URL when visiting the "Solution and commentary" page. Alternatively, make another redirect.
3. No effect on 1992-1999 crosswords
    - This would require another pair of redirects (or maybe cleverer Regex patterns?), which I'm leaving as exercise for the reader as I didn't want to influence the behavior for pre-Shortz crosswords.
3. The site does not work on mobile
    - It would take more effort than just 2 regular expressions (userscript or full browser extension) to add a virtual (JS) keyboard to XWord Info or modify an existing online app to use XWI's data. That solution would be more robust as it could evade blocking attempts by XWI (as long as they continue providing full solutions & analyses on their main page). 
