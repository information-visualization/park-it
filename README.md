# ParkIt
A mobile-based application that assists local citizens commuting to the CBD in finding parking. The app displays occupancy data for different parking bays around the city, in real-time, and can be filtered based on cost, permitted parking duration, distance to be walked from destination, and whether the bay supports drivers with disability needs.

[Live Demo](https://parkit.shinyapps.io/park-it/)
![screenshot](/doc/ParkIt.gif)

## Contributors

  <a href="https://github.com/johnsonjzhou">
    <img src="https://contrib.rocks/image?repo=johnsonjzhou/mycirclepackage" />
  </a>
  <a href="https://github.com/jkengs">
    <img src="https://contrib.rocks/image?repo=information-visualization/park-it" />
  </a>
<!-- Made with contrib.rocks -->

## Run App

> This app uses CSS style that are not supported by the built-in browser of RStudio. For best experience, please use an external (modern) browser.

### Install dependencies
```R
source("./R/libraries.R")
```

### Running the Shiny App
```R
# At the root project directory
shiny::runApp()
```

### Running the Shiny App silently
```R
shiny::runApp(launch.browser = FALSE)
```

## Building

### Directory tree
```
root
  |- data: data sources for the dash board
  |- doc: documentation
  |- R: supporting R scripts for the app
  |- src: supporting non-R source files and assets
  |- www: production non-R files and assets for use by the app
```

### Building supporting (non-R) source files (optional)
Non-R source files are built using `webpack`, 
transforming from `./src` to `./www`.  
```bash
# install node module
npm install

# build
npm run build
```

### Deployment to shinyapps.io
Use script `deploy.R` and ensuring to change the following parameters:
```R
deploy <- list(
  "account" = "CHANGEME",
  "token" = "CHANGEME",
  "secret" = "CHANGEME",
  "appName" = "parkit"
)
```
## Data Source
[CoM Data](https://www.data.vic.gov.au)
