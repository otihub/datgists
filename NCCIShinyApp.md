+ Navigate to NCCI folder; set as working directory

`setwd('go/to/NCCI')`

+ Run [limerscript.R](https://raw.githubusercontent.com/snurhussein/NCCI/master/limerscript.R) or copy code into console to download and consolidate new surveys

+ Follow instructions in [App.R](https://raw.githubusercontent.com/snurhussein/NCCI/master/app.R) to update App with new surveys

+ Configure shiny account

`rsconnect::setAccountInfo(name="<ACCOUNT>", token="<TOKEN>", secret="<SECRET>")`

+ Download App.R to working directory and Run

`rsconnect::deployApp('path/to/NCCI')`
