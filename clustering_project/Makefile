# Makefile for BIOS611 Clustering Analysis Project

.PHONY: all clean install_packages render

# Default target: run everything
all: install_packages render

# Install required R packages
install_packages:
	@echo "Installing required R packages..."
	Rscript -e "if (!require('cluster')) install.packages('cluster', repos='http://cran.us.r-project.org')"
	Rscript -e "if (!require('ggplot2')) install.packages('ggplot2', repos='http://cran.us.r-project.org')"
	Rscript -e "if (!require('plotly')) install.packages('plotly', repos='http://cran.us.r-project.org')"
	Rscript -e "if (!require('dplyr')) install.packages('dplyr', repos='http://cran.us.r-project.org')"
	Rscript -e "if (!require('tidyr')) install.packages('tidyr', repos='http://cran.us.r-project.org')"
	Rscript -e "if (!require('htmlwidgets')) install.packages('htmlwidgets', repos='http://cran.us.r-project.org')"
	Rscript -e "if (!require('rmarkdown')) install.packages('rmarkdown', repos='http://cran.us.r-project.org')"
	Rscript -e "if (!require('knitr')) install.packages('knitr', repos='http://cran.us.r-project.org')"
	@echo "Package installation complete."

# Render RMarkdown to HTML and extract figures
render: ClusterTask.html

ClusterTask.html: ClusterTask.Rmd
	@echo "Rendering ClusterTask.Rmd..."
	Rscript -e "rmarkdown::render('ClusterTask.Rmd', output_format = 'html_document')"
	@echo "Render complete: ClusterTask.html"

# Clean generated files
clean:
	@echo "Cleaning generated files..."
	rm -f ClusterTask.html
	rm -rf ClusterTask_files/
	rm -f *.png *.csv
	rm -f Rplots.pdf
	@echo "Clean complete."

# Help target
help:
	@echo "BIOS611 Clustering Analysis - Available targets:"
	@echo "  make all              - Install packages and render RMarkdown"
	@echo "  make install_packages - Install required R packages"
	@echo "  make render           - Render ClusterTask.Rmd to HTML"
	@echo "  make clean            - Remove generated files"
	@echo "  make help             - Show this help message"