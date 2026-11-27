# LIBS Lithium Comparison

**Open the tool: https://nrflagg.github.io/libs-lithium/**

A single-page tool for LIBS `.tdms` spectra. Open `index.html` in a browser (or the GitHub Pages address for this repository) and drop files onto it. Everything runs in the browser; no data is uploaded.

Choose what you're running at the top of the page; each choice has its own link:

- Comparing samples: https://nrflagg.github.io/libs-lithium/#compare
- An experiment (conditions such as time, pH, salinity): https://nrflagg.github.io/libs-lithium/#experiment
- A sediment core (depth, plotted as a downhole profile): https://nrflagg.github.io/libs-lithium/#core
- Mapping a rock (microscope images, micro-XRF maps): https://nrflagg.github.io/libs-lithium/#map

What it does:

- Converts each `.tdms` file to CSV (one column per channel, the same layout as `nptdms` `as_dataframe().to_csv()`).
- Measures Li I 670.78 nm in each sample and ranks samples against one another, with the spread across grid locations.
- Plots relative lithium for every sample as a scatter, with each grid location shown and the mean ± one standard deviation.
- When you import files, asks for each sample's conditions (experiment) or depth (core), typed in or loaded from a CSV.
- Lets you give each sample values for experimental variables (time, pH, salinity, depth, or any other), typed in or loaded from a CSV, and plot lithium against any of them.
- Checks the 610.3 nm feature for calcium (Ca I 610.27 overlaps Li I 610.36) using Ca I 612.22.
- Flags peaks near the detector ceiling and flat-topped peaks.
- Maps the LIBS spots in stage coordinates over microscope images and micro-XRF maps. Images are registered either by pixel size and corner position or by clicking points of known stage position; spot positions come from the file when it records them, or from a grid you describe (columns, spacing, row-by-row or back-and-forth). Spots are coloured by lithium, a companion element, or a ratio, and can be compared with the micro-XRF value under each spot.
- Micro-XRF maps: a CSV/TXT table of numbers (one map row per line) or a greyscale PNG/JPEG.
- Tracks companion elements chosen from a periodic table, and plots lithium against any of them.

Notes:

- Sample-value CSV: first column is the sample (file) name, then one column per value, e.g. `sample,time (h),pH,salinity (g/L)` or `sample,depth (cm)`. Drop it on the page with the `.tdms` files. Depths in mm, cm or m are converted to the page's depth unit.
- Results are relative intensities for comparing similar samples. They are not concentrations until calibration standards are added.
- The detector ceiling defaults to 65,535 counts; change it under Analysis settings if your spectrometer differs.
- Line wavelengths are air wavelengths in nm and are listed in the `LINES` table near the top of the script in `index.html`.

## License

MIT. See `LICENSE`.
