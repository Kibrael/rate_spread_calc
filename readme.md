### This repository contains a prototype rate-spread calculator for use with HMDA data.

Rate-spread information is required for originated loans exceeding a specific threshold based on lien type (1.5 for first and 3.5 for subordinate).

Rate spread is determined by subtracting the appropriate APOR from the loan's APR. The APOR tables are available at [www.ffiec.gov](https://www.ffiec.gov/ratespread/aportables.htm). APOR numbers are published weekly for variable and fixed rate terms between 1 and 50 years. The variable rate term is the number of years prior to the first rate reset. In determing rate-spread the APOR of the week in which the interest rate of the loan was locked in is used.  
 
**The prototype calculator requires the following inputs:**
- **term**: a string between 1 and 50 indicating the term of a fixed rate loan or periods prior to the first rate reset of a variable rate loan
- **lock_date**: a string object in format '2015-08-29' indicating the date the interest rate was locked in
- lien: the lien status of the loan, valid values are 1, 2, 3, 4 (only 1 and 2 will return a rate spread, 3 and 4 return NA)
- **amort**: a string indicating the amortization type of the loand (valid values are 'fixed' and 'variable')
- **apr**: the APR of the loan as determined by the applicable regulations
