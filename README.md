# optimal-leverage

Worst case analysis for UPRO relative to the S&P 500

Consider an initial date.  You invest $10,000 in SPX and $10,000 in UPRO.  Then the "sunshine" date is the date on which your investment in UPRO is thereafter never less valuable than your investment in SPX.

The output Excel file is 247.5MB.  Github will not allow upload of a file larger than 25MB.

To do:
1. Compare Excel file against Morningstar to confirm algorithm correctness.
2. Combine the regression notebook with the compounding notebook and remove hard-coded bits.  Check whether the input files can be downloaded from Yahoo programatically.
3. Presently the analysis involves no rebalancing.  Check the effect of rebalancing on the time to sunshine and total return.  Candidates for rebalancing include BND, ANGL, and SPY.  Parameters include candidate, period, and percentage.
4. Translate code to Julia and implement multicore processing.  Determining the daily compounding matrix is processor-bound and done once for each security.  The write to Excel is processor-bound and involves two independent dataframes.  Optimizing rebalancing runtime is linear in three additional variables and depends on granularity.
