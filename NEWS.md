# rFIA v1.1.0

+ Jeff Doser is the new package maintainer. Please send all inquiries via email to Jeff (jwdoser@ncsu.edu) or post potential bugs on the GitHub development page.  
+ Updated the `fiaRI` object to reflect recent changes in the FIA Database. These changes resulted in the package functions successfully working with the previous version of `fiaRI` but not working for actual user data when pulling data from recent versions of the FIA Database.
+ Updated functionality for working with external spatial (`sf`) objects with the following functions: `tpa()`. Changes in recent versions of the `sf` package led to errors when attempting to return a spatial object. This bug is now fixed.
+ Substantial updates to `biomass()`. Previous versions were not compatible with updates in FIADB and the new National Scale Volume and Biomass (NSVB) estimators. The function is now updated and returns biomass and carbon estimates using the NSVB procedure. 
+ Updated `findEVALID()` to return the correct evaluation IDs. Previous versions had an incorrect join that resulted in additional, incorrect EVALIDs being returned for a given set of criteria. This function should only be used by users familiar with FIA and desiring to use FIA data for use outside of `rFIA`, as `rFIA` is built in a way that users do not need to directly interact with EVALIDs. 
+ Updated `dwm()` when `byPlot = TRUE` to set the `YEAR` column equal to the year each plot was measured (`MEASYEAR`), which may differ slightly from its associated inventory year (`INVYR`). This is what all other `rFIA` functions do and what was reported in the manual, but the `YEAR` returned prior to this version was actually the inventory year. 
+ Fixed a bug with `growMort()` that resulted in estimates of mean annual survivor growth and mean annual net change reporting as 0.  
+ Fixed a typo in the `standStruct()` documentation that incorrectly said the lower diameter for Pole class was set at 11cm while it is in fact set at 12.7cm (5in).  
+ Fixed typo in documentation of `plotFIA()` regarding the error bars produced when `se = TRUE`. These are 95% confidence intervals, not 68% confidence intervals.
+ Added more details to `vegStruct()` on reporting of estimates by canopy layer and growth habit.
+ Updated internal data to now contain the Dec 2024 `REF_SPECIES` table from FIADB, which provides access to the `CARBON_RATIO_LIVE` attribute for using the NSVB species-specific carbon fractions. 
