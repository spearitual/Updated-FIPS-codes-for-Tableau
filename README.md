# Updated-FIPS-codes-for-Tableau
Table for updating FIPS codes (USA county codes) to work with Tableau 2024.1

When accessing older data on US counties, you may sometimes find that some of the FIPS codes provided are not recognized by Tableau, or are otherwise problematic.

Sometimes it is problematic because the FIPS is outdated, sometimes because it is a combination of counties (such as those used by BEA), and sometimes because it is an uncombined county you actually want to combine.

This table catalogs all the problematic FIPS codes I have discovered, as well as the nearest modern equivalents I could find.

Note that displaying data for extinct counties according to modern borders is inherently imprecise. However, it may sometimes be the best option. I hope you find this table useful in such situations.

If you find an error or have an addition to make, please don't hesitate to let me know. 

Terms:
*old_FIPS: This is the original FIPS code.
*new_FIPS: This is my primary suggestion for updating the original FIPS. In the case of the original FIPS being outdated, this is the nearest modern equivalent to the county of the old FIPS (in the case of a county being split, it is the largest of the resulting counties, by land area). In the case of combined counties, it is the county in that combination (i.e., not the independent city, but the surrounding county). In the case of the FIPS of independent cities, it is the FIPS of the surrounding county. All new_FIPS are recognized by Tableau, as of 2024-05-18.
*new_FIPS_2: This is my secondary suggestion, if any. In the case of being outdated, it is the second-largest county in the split. In the case of combined counties, it is the first independent city, alphabetically sorted. In the case of the FIPS of independent cities, it is the FIPS of the combination of that city with its surrounding county (and the other city, if any). Note the combined FIPS will not be recognized by Tableau.
*new_FIPS_3: My tertiary suggestion, if any. In the case of combined counties, it is the next independent city in alphabetical order. In the case of the FIPS of independent cities, it is the other city involved in the combination.
*old_name: This is the original name of the county.
*new_name: This is the name of the county associated with new_FIPS. If a county's FIPS is updated, Tableau will recognize it, even if the name is not updated, but you may still wish to do so.
*new_name_2: The name of new_FIPS_2.
*new_name_3: The name of new_FIPS_3.
*state: The name of the state the county is in.
*date: The effective date for the FIPS code becoming outdated. If there is no date, that indicated that the FIPS code is still in use.
*border_change: If True, old_FIPS and new_FIPS do not refer to the exact same area. If False, they do (meaning the change was in name and FIPS only).
*reason: This indicates the source of the problem. "outdated" indicates the FIPS is no longer in use. "combination" indicates that old_FIPS refers to a combination of counties, rather than any single one. "unmerged" indicates that the old_FIPS is not combined with any county, when you may desire it to be.
*recognized: This indicates whether Tableau recognizes the old_FIPS at all. If False, it does not. If True, it does.
displayed_correctly: This indicates whether Tableau correctly displays the old_FIPS. If False, it does not. If True, it does.

Note for Connecticut counties: These are the only counties Tableau currently recognizes but does not display correctly, and are therefore perhaps the most important to update. The new_FIPS for each of these counties is based on how Tableau displays them, which is more or less the most accurate option, with one exception. Both Hartford County (09003) and Tolland County (09013) are displayed as South Central Connecticut Planning Region (09170). This causes overlap of the displayed data, which can cause significant issues. Therefore I've chosen the new_FIPS of Tolland County to instead be Capitol Planning Region (09110), the nearest available county. 

Sources:
https://www.census.gov/programs-surveys/geography/technical-documentation/county-changes/1980.html

https://www.census.gov/programs-surveys/geography/technical-documentation/county-changes/1990.html

https://cdc.gov/nchs/nvss/bridged_race/county_geography-_changes1990-present.pdf

https://www.ddorn.net/data/FIPS_County_Code_Changes.pdf

https://www.economy.com/support/blog/getfile.asp?did=869A03D1-5D74-4376-A606-00A8C64DDB0B&fid=a18d6d4873834f749d42ded633850a5e.xlsx

https://www.federalregister.gov/documents/2022/06/06/2022-12063/change-to-county-equivalents-in-the-state-of-connecticut
