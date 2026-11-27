# LIBS Lithium Comparison

**Open the tool: https://nrflagg.github.io/libs-lithium/**

A single-page tool for LIBS `.tdms` spectra. Open `index.html` in a browser (or the GitHub Pages address for this repository) and drop files onto it. Everything runs in the browser; no data is uploaded.

What it does:

- Converts each `.tdms` file to CSV (one column per channel, the same layout as `nptdms` `as_dataframe().to_csv()`).
- Measures Li I 670.78 nm in each sample and ranks samples against one another, with the spread across grid locations.
- Plots relative lithium for every sample as a scatter, with each grid location shown and the mean ± one standard deviation.
- When you import files from an experiment, asks you to type in each sample's conditions (time, pH, salinity, or any variable you add).
- Lets you give each sample values for experimental variables (time, pH, salinity, depth, or any other), typed in or loaded from a CSV, and plot lithium against any of them.
- Checks the 610.3 nm feature for calcium (Ca I 610.27 overlaps Li I 610.36) using Ca I 612.22.
- Flags peaks near the detector ceiling and flat-topped peaks.
- Tracks companion elements chosen from a periodic table, and plots lithium against any of them.

Notes:

- Sample-variable CSV: first column is the sample (file) name, then one column per variable, e.g. `sample,time (h),pH,salinity (g/L)`. Drop it on the page with the `.tdms` files.
- Results are relative intensities for comparing similar samples. They are not concentrations until calibration standards are added.
- The detector ceiling defaults to 65,535 counts; change it under Analysis settings if your spectrometer differs.
- Line wavelengths are air wavelengths in nm and are listed in the `LINES` table near the top of the script in `index.html`.

## License

MIT. See `LICENSE`.
