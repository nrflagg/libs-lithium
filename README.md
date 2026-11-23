# LIBS Lithium Comparison

A single-page tool for LIBS `.tdms` spectra. Open `index.html` in a browser (or the GitHub Pages address for this repository) and drop files onto it. Everything runs in the browser; no data is uploaded.

What it does:

- Converts each `.tdms` file to CSV (one column per channel, the same layout as `nptdms` `as_dataframe().to_csv()`).
- Measures Li I 670.78 nm in each sample and ranks samples against one another, with the spread across grid locations.
- Checks the 610.3 nm feature for calcium (Ca I 610.27 overlaps Li I 610.36) using Ca I 612.22.
- Flags peaks near the detector ceiling and flat-topped peaks.
- Tracks companion elements chosen from a periodic table, and plots lithium against any of them.

Notes:

- Results are relative intensities for comparing similar samples. They are not concentrations until calibration standards are added.
- The detector ceiling defaults to 65,535 counts; change it under Analysis settings if your spectrometer differs.
- Line wavelengths are air wavelengths in nm and are listed in the `LINES` table near the top of the script in `index.html`.
