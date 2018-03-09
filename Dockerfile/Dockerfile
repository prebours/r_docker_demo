FROM r-base

# install system dependencies
RUN apt-get update && apt-get install -y \
	curl \
	libcurl4-openssl-dev \
	libmariadb-client-lgpl-dev \
	libpq-dev \
	libssl-dev \
	libxml2-dev \
	openjdk-8-jdk \
	pandoc \
	texlive-latex-base \
	texlive-latex-extra \
	texlive-latex-recommended \
	wget


# setup java
ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64
ENV LD_LIBRARY_PATH=$JAVA_HOME/jre/lib/amd64
RUN R CMD javareconf

# install base packages
ENV REPOS=https://cloud.r-project.org

RUN R -e "install.packages(c('roxygen2', 'testthat', 'stringr', 'dplyr', 'DBI', 'tidyr', 'stringi', 'stringr', 'lubridate', 'magrittr', 'digest', 'tools', 'R.utils', 'devtools', 'rworldmap', 'spam', 'XLConnectJars', 'XLConnect', 'htmltools', 'ggthemes', 'gtable', 'ggplot2', 'plotly', 'DT', 'rgexf', 'DiagrammeR', 'googleVis', 'rmarkdown', 'pander', 'zoo', 'RMySQL', 'RPostgreSQL', 'threejs', 'shiny', 'shinyjs', 'rmarkdown', 'shinydashboard', 'httr', 'jsonlite', 'curl', 'readr', 'rJava', 'ggmap', 'R6', 'sp', 'geosphere', 'leaflet', 'maptools', 'whisker', 'pryr', 'viridis', 'openssl', 'rvest', 'purrr', 'compare', 'tibble', 'googlesheets', 'XML', 'mapproj', 'readxl', 'Cairo', 'checkmate', 'foreach', 'doSNOW', 'snow', 'feather', 'ISOcodes', 'iptools'), repos='$REPOS')"

