# FTIRbaselines
Processes FTIR spectra of natural organic matter by finding exact peak locations, baseline-correcting the peaks, and converting them to relative abundances.

## Current version

Please have a look at [irpeat](https://github.com/henningte/irpeat) for a current implementation of the script. This repository no longer is maintained.

## Modifications
This (file: FTIRbaselines_1) is a modified version of the original script (file: FTIRbaselines.R) by Suzanne Hodgkins and Florida State University. Modifications were done by Henning Teickner (contact: h_teic01@wwu.de). 

The modifications ensure that non-integer valued wavenumbers of IR spectra and integer valued wavenumbers of IR spectra that are not spaced by values of one can be processed by linearly interpolating the absorbance values for integer valued wavenumbers. Modified parts are introduced by # "MODIFIED START" and the end of modified parts is marked with # "MODIFIED END" throughout the script. 

For modified parts, the copyright is © 2018 Henning Teickner and they are free under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. The modified parts and the rest of the program are distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.

## Overview

This script finds the exact wavenumber locations of specific peaks in FTIR spectra of natural organic matter (such as plants and peat soils). It then baseline-corrects the peaks and converts them into relative abundances (relative to the integrated area of the whole spectrum). It does this for the following peaks (approx. wavenumbers in cm<sup>-1</sup>):

- carb (1030): carbohydrates
- arom15 (1510): aromatics
- arom16 (1630) : aromatics, or deprotonated COO-
- acids (1720): protonated COOH
- aliph28 (2850): aliphatics, lipids, and waxes
- aliph29 (2920): aliphatics, lipids, and waxes

New in this version (Jan. 27, 2017): Also calculates areas for each peak, and exports as CSVs called Raw.Areas, Corr.Areas, Norm.Raw.Areas, and Norm.Corr.Areas (defined similarly to the peak height files). Filenames of peak height output files have also been changed to avoid confusing them with the area files. For peaks that share the same baseline, the baseline remains unchanged and the areas are defined between each endpoint and the trough between the peaks. So to get the total area of the aliphatic region (for example), add the areas of the aliph28 and aliph29 peaks.

For details on the use of this program, including a tutorial and description of all output files, see the included file "procedure for R program.docx".

An example dataset is included in the file "example_data.csv". Humification indices for these spectra (based on fixed wavenumbers, not using this script) are published in the following manuscript:
Hodgkins S. B., Tfaily M. M., McCalley C. K., Logan T. A., Crill P. M., Saleska S. R., Rich V. I. and Chanton J. P. (2014) Changes in peat chemistry associated with permafrost thaw increase greenhouse gas production. Proc. Natl. Acad. Sci. USA 111, 5819–5824.

## Licensing

### License of the original version

Copyright: © 2017 Suzanne Hodgkins and Florida State University.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.  If not, see <http://www.gnu.org/licenses/>.

### License for the modified parts

For modified parts, the copyright is © 2018 Henning Teickner and they are free under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. The modified parts and the rest of the program are distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.
