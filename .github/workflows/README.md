# GitHub Actions Workflows

## Generate Station Map

The `generate-station-map.yml` workflow automatically generates and updates the station map image used in the README.

### When it runs:

- **On push**: When changes are made to `src/dwd_opendata/__init__.py` or the workflow file itself
- **Monthly schedule**: First day of each month to keep the map current with DWD data
- **Manual trigger**: Can be triggered manually from the Actions tab

### What it does:

1. Sets up Ubuntu with required system dependencies (libgeos, libproj for cartopy)
2. Installs uv and Python 3.13
3. Installs project dependencies
4. Runs the example code to generate the station map
5. Saves the map to `images/station_map.png`
6. Commits and pushes the updated image if it changed

### Note:

The commit message includes `[skip ci]` to prevent infinite loops of the action triggering itself.
