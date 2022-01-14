# MHIRA patient reporting tool
This is a shiny app which serves as a patient data reporting tool for the Mental Health Information Reporting Assisitant (MHIRA).  
MHIRA allows for the connection of external apps for reporting by adding these apps to the [docker setup](https://www.docker.com/) in which MHIRA is shipped.
In this case, reporting is done with [shiny](https://www.rstudio.com/products/shiny/shiny-server/).

## How it works

The [MHIRA docker installation](https://github.com/mhira-project/mhira-docker) comes with a shiny server in a [docker container](https://hub.docker.com/r/rocker/shiny-verse).

When installing MHIRA, settings can be modified in the .env file (see [MHIRA installation reporitory](https://github.com/mhira-project/mhira-docker)).
The .env file contains the setting for the data save path. 

After installation of MHIRA, you will find a folder called 'shiny' under the data save path. Under the initial settings, this will be: '.mhira-docker/data/shiny'. 
For the app in the current repository to work, you need to copy it to the 'apps' folder inside this folder.

It should then look like this: 

'.mhira-docker/data/shiny/apps/patient-report'

Now the shiny app should be available under the url 'localhost/shiny' which you can enter to your local browser. 

The app will not yet work, because it expects addtional parameters in the url. 

You can use the app pressing the reporting button in the MHIRA application. This will redirect you to the shiny app you just installed. 


# Troubleshooting of the shiny app in the shiny container

If you want to see output from the shiny app you can attach the container to your terminal using 

docker attach to attach the shiny docker container e.g. 'docker attach mhira-docker_shiny1'.
