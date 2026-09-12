# GMT Clip Areas — Coastline-Based Raster Clipping Scripts

GMT (Generic Mapping Tools) shell scripts demonstrating coastline-based raster clipping, where a coastline clip path is used to display one dataset over the ocean and a differently styled version over the masked land. In these examples a colour geoid is shown over the sea with gray-shaded topography over land, a cartographic technique that emphasises marine data. The examples cover the Kuril-Kamchatka and Mariana Trenches and support figures in the author's geophysical and cartographic publications.

## What the scripts do

- generate a colour palette and render the primary dataset (geoid) over the full extent (grd2cpt, grdimage) with contours (grdcontour)
- initiate a coastline clip path for land (pscoast -Gc)
- render a second, gray-shaded dataset inside the land clip (makecpt, grdimage)
- undo the clip path and overlay the basemap frame (pscoast -Q)
- add shoreline contours, grid, colour scale bar, scale bar and directional rose (grdcontour, psbasemap, psscale)
- add the GMT logo (logo) and clean up temporary CPTs (rm)
- export to raster (psconvert) at high resolution

## Data sources

Geoid from EGM96, relief/bathymetry from ETOPO1. Coastlines from GSHHG via GMT.

## Files

- GMT-21-script-JM-clip-KKT.sh: Kuril-Kamchatka Trench
- GMT-21-script-JM-clip-MT.sh: Mariana Trench

## Requirements

- GMT 6.x (Generic Mapping Tools): https://www.generic-mapping-tools.org
- A POSIX shell (bash)
- The relevant geoid / relief grid(s) available locally

## Usage

Place the required grid in the working directory, adjust the -R region and -J projection at the top of the chosen script, then run:

    bash GMT-21-script-JM-clip-MT.sh

The script writes a PostScript file and converts it to a raster image (JPG/PNG) via psconvert.

## Author and citation

Polina Lemenkova
ORCID: https://orcid.org/0000-0002-5759-1089

These scripts support figures in the author's geophysical and cartographic papers; please cite the specific article a given figure appears in. The full publication list is available via the ORCID record above.

## License

See the LICENSE file in this repository.
