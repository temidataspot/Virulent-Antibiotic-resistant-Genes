# Research Questions and Analytical Solutions
The purpose of this analysis is to compare the prevalence of resistant and virulent genes
and how they contribute to different antibiotic sensitivity.

Comparative analysis was conducted for the five Aeromonas species listed in the overview of this project

** General Steps:**
- Install necessary packages and load required libraries
- Upload necessary files and assign dataframes for virulent and resistant genes
- Add max and min for the chart scaling
- Set up and plot radar chart

** This process is repeated for the five Aeromonas species studied

# Aeromonas hydrophila

```r
# Load required library
library(fmsb)

# Prepare data for Virulence genes and Resistance genes in a single data frame
# Virulence genes data
virulence_data <- data.frame(
  Aerolysin = 60,
  Elastase = 40,
  Haemolysin = 80,
  Lipase = 100,
  Serin_Protease = 80,
  Nuclease = 40,
  TET_A = NA,   # Resistance genes, set as NA for Virulence
  TET_B = NA,
  AMP_C = NA,
  "blaCTX-M" = NA,
  "bla-SHV" = NA,
  "bla-TEM" = NA,
  Intergerons1 = NA,
  Sul = NA
)

# Resistance genes data
resistance_data <- data.frame(
  Aerolysin = NA,   # Virulence genes, set as NA for Resistance
  Elastase = NA,
  Haemolysin = NA,
  Lipase = NA,
  Serin_Protease = NA,
  Nuclease = NA,
  TET_A = 80,   # Resistance genes, set as NA for Virulence
  TET_B = 60,
  AMP_C = 100,
  "blaCTX-M" = 100,
  "bla-SHV" = 100,
  "bla-TEM" = 20,
  Intergerons1 = 60,
  Sul = 20
)

# Add max and min for the chart scaling (for both virulence and resistance)
max_min_data <- data.frame(
  Aerolysin = c(100, 0),
  Elastase = c(100, 0),
  Haemolysin = c(100, 0),
  Lipase = c(100, 0),
  Serin_Protease = c(100, 0),
  Nuclease = c(100, 0),
  TET_A = c(100, 0),
  TET_B = c(100, 0),
  AMP_C = c(100, 0),
  "blaCTX-M" = c(100, 0),
  "bla-SHV" = c(100, 0),
  "bla-TEM" = c(100, 0),
  Intergerons1 = c(100, 0),
  Sul = c(100, 0)
)

# Combine the data with the max-min values for scaling
data_radar <- rbind(max_min_data, virulence_data, resistance_data)

# Set up the radar chart
par(mar = c(3, 3, 3, 3))  # Adjust margins

# Plot the radar chart
radarchart(
  data_radar, 
  axistype = 1,
  pcol = c("blue", "green"),  # Line colors: blue for virulence, green for resistance
  pfcol = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)),  # Fill colors for each
  plwd = 2,  # Line width
  cglcol = "grey", cglty = 1, axislabcol = "black", caxislabels = seq(0, 100, 25), cglwd = 0.8,
  vlcex = 0.8
)
# Add a title
title(main = "Comparing Virulence and Resistance Genes in A. hydrophila")

# Add a legend
legend(x = "topright", legend = c("Virulence genes", "Resistance genes"), 
       fill = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)), cex = 0.8)
```
[image](https://github.com/temidataspot/Virulent-Antibiotic-resistant-Genes/blob/main/A.hydrophila.png)

# Aeromonas Caviae

```r
# Load required library
library(fmsb)

# Prepare data for Virulence genes and Resistance genes in a single data frame
# Virulence genes data
virulence_data <- data.frame(
  Aerolysin = 25,
  Elastase = 12,
  Haemolysin = 50,
  Lipase = 38,
  Serin_Protease = 88,
  Nuclease = 29,
  TET_A = NA,   # Resistance genes, set as NA for Virulence
  TET_B = NA,
  AMP_C = NA,
  "blaCTX-M" = NA,
  "bla-SHV" = NA,
  "bla-TEM" = NA,
  Intergerons1 = NA,
  Sul = NA
)

# Resistance genes data
resistance_data <- data.frame(
  Aerolysin = NA,   # Virulence genes, set as NA for Resistance
  Elastase = NA,
  Haemolysin = NA,
  Lipase = NA,
  Serin_Protease = NA,
  Nuclease = NA,
  TET_A = 88,   # Resistance genes, set as NA for Virulence
  TET_B = 25,
  AMP_C = 100,
  "blaCTX-M" = 100,
  "bla-SHV" = 75,
  "bla-TEM" = 14,
  Intergerons1 = 13,
  Sul = 0
)

# Add max and min for the chart scaling (for both virulence and resistance)
max_min_data <- data.frame(
  Aerolysin = c(100, 0),
  Elastase = c(100, 0),
  Haemolysin = c(100, 0),
  Lipase = c(100, 0),
  Serin_Protease = c(100, 0),
  Nuclease = c(100, 0),
  TET_A = c(100, 0),
  TET_B = c(100, 0),
  AMP_C = c(100, 0),
  "blaCTX-M" = c(100, 0),
  "bla-SHV" = c(100, 0),
  "bla-TEM" = c(100, 0),
  Intergerons1 = c(100, 0),
  Sul = c(100, 0)
)

# Combine the data with the max-min values for scaling
data_radar <- rbind(max_min_data, virulence_data, resistance_data)

# Set up the radar chart
par(mar = c(3, 3, 3, 3))  # Adjust margins

# Plot the radar chart
radarchart(
  data_radar, 
  axistype = 1,
  pcol = c("blue", "green"),  # Line colors: blue for virulence, green for resistance
  pfcol = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)),  # Fill colors for each
  plwd = 2,  # Line width
  cglcol = "grey", cglty = 1, axislabcol = "black", caxislabels = seq(0, 100, 25), cglwd = 0.8,
  vlcex = 0.8
)
# Add a title
title(main = "Comparing Virulence and Resistance Genes in A. caviae")

# Add a legend
legend(x = "topright", legend = c("Virulence genes", "Resistance genes"), 
       fill = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)), cex = 0.8)
```

# Aeromas Veroni

```r
# Load required library
library(fmsb)

# Prepare data for Virulence genes and Resistance genes in a single data frame
# Virulence genes data
virulence_data <- data.frame(
  Aerolysin = 43,
  Elastase = 43,
  Haemolysin = 43,
  Lipase = 43,
  Serin_Protease = 43,
  Nuclease = 29,
  TET_A = NA,   # Resistance genes, set as NA for Virulence
  TET_B = NA,
  AMP_C = NA,
  "blaCTX-M" = NA,
  "bla-SHV" = NA,
  "bla-TEM" = NA,
  Intergerons1 = NA,
  Sul = NA
)

# Resistance genes data
resistance_data <- data.frame(
  Aerolysin = NA,   # Virulence genes, set as NA for Resistance
  Elastase = NA,
  Haemolysin = NA,
  Lipase = NA,
  Serin_Protease = NA,
  Nuclease = NA,
  TET_A = 86,   # Resistance genes, set as NA for Virulence
  TET_B = 29,
  AMP_C = 100,
  "blaCTX-M" = 100,
  "bla-SHV" = 86,
  "bla-TEM" = 14,
  Intergerons1 = 0,
  Sul = 14
)

# Add max and min for the chart scaling (for both virulence and resistance)
max_min_data <- data.frame(
  Aerolysin = c(100, 0),
  Elastase = c(100, 0),
  Haemolysin = c(100, 0),
  Lipase = c(100, 0),
  Serin_Protease = c(100, 0),
  Nuclease = c(100, 0),
  TET_A = c(100, 0),
  TET_B = c(100, 0),
  AMP_C = c(100, 0),
  "blaCTX-M" = c(100, 0),
  "bla-SHV" = c(100, 0),
  "bla-TEM" = c(100, 0),
  Intergerons1 = c(100, 0),
  Sul = c(100, 0)
)

# Combine the data with the max-min values for scaling
data_radar <- rbind(max_min_data, virulence_data, resistance_data)

# Set up the radar chart
par(mar = c(3, 3, 3, 3))  # Adjust margins

# Plot the radar chart
radarchart(
  data_radar, 
  axistype = 1,
  pcol = c("blue", "green"),  # Line colors: blue for virulence, green for resistance
  pfcol = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)),  # Fill colors for each
  plwd = 2,  # Line width
  cglcol = "grey", cglty = 1, axislabcol = "black", caxislabels = seq(0, 100, 25), cglwd = 0.8,
  vlcex = 0.8
)
# Add a title
title(main = "Comparing Virulence and Resistance Genes in A. veroni")

#Add a legend

legend(x = "topright", legend = c("Virulence genes", "Resistance genes"), 
       fill = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)), cex = 0.8)
```

# Aeromonas allosaccharophila

```r
# Load required library
library(fmsb)

# Prepare data for Virulence genes and Resistance genes in a single data frame
# Virulence genes data
virulence_data <- data.frame(
  Aerolysin = 0,
  Elastase = 33,
  Haemolysin = 33,
  Lipase = 0,
  Serin_Protease = 33,
  Nuclease = 43,
  TET_A = NA,   # Resistance genes, set as NA for Virulence
  TET_B = NA,
  AMP_C = NA,
  "blaCTX-M" = NA,
  "bla-SHV" = NA,
  "bla-TEM" = NA,
  Intergerons1 = NA,
  Sul = NA
)

# Resistance genes data
resistance_data <- data.frame(
  Aerolysin = NA,   # Virulence genes, set as NA for Resistance
  Elastase = NA,
  Haemolysin = NA,
  Lipase = NA,
  Serin_Protease = NA,
  Nuclease = NA,
  TET_A = 100,   # Resistance genes, set as NA for Virulence
  TET_B = 33,
  AMP_C = 100,
  "blaCTX-M" = 100,
  "bla-SHV" = 67,
  "bla-TEM" = 0,
  Intergerons1 = 0,
  Sul = 33
)

# Add max and min for the chart scaling (for both virulence and resistance)
max_min_data <- data.frame(
  Aerolysin = c(100, 0),
  Elastase = c(100, 0),
  Haemolysin = c(100, 0),
  Lipase = c(100, 0),
  Serin_Protease = c(100, 0),
  Nuclease = c(100, 0),
  TET_A = c(100, 0),
  TET_B = c(100, 0),
  AMP_C = c(100, 0),
  "blaCTX-M" = c(100, 0),
  "bla-SHV" = c(100, 0),
  "bla-TEM" = c(100, 0),
  Intergerons1 = c(100, 0),
  Sul = c(100, 0)
)

# Combine the data with the max-min values for scaling
data_radar <- rbind(max_min_data, virulence_data, resistance_data)

# Set up the radar chart
par(mar = c(3, 3, 3, 3))  # Adjust margins

# Plot the radar chart
radarchart(
  data_radar, 
  axistype = 1,
  pcol = c("blue", "green"),  # Line colors: blue for virulence, green for resistance
  pfcol = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)),  # Fill colors for each
  plwd = 2,  # Line width
  cglcol = "grey", cglty = 1, axislabcol = "black", caxislabels = seq(0, 100, 25), cglwd = 0.8,
  vlcex = 0.8
)
# Add a title
title(main = "Comparing Virulence and Resistance Genes in A. allosaccharophila")

#Add a legend

legend(x = "topright", legend = c("Virulence genes", "Resistance genes"), 
       fill = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)), cex = 0.8)
```

# Aeromonas dhakensis

```r
# Load required library
library(fmsb)

# Prepare data for Virulence genes and Resistance genes in a single data frame
# Virulence genes data
virulence_data <- data.frame(
  Aerolysin = 50,
  Elastase = 0,
  Haemolysin = 50,
  Lipase = 0,
  Serin_Protease = 50,
  Nuclease = 50,
  TET_A = NA,   # Resistance genes, set as NA for Virulence
  TET_B = NA,
  AMP_C = NA,
  "blaCTX-M" = NA,
  "bla-SHV" = NA,
  "bla-TEM" = NA,
  Intergerons1 = NA,
  Sul = NA
)

# Resistance genes data
resistance_data <- data.frame(
  Aerolysin = NA,   # Virulence genes, set as NA for Resistance
  Elastase = NA,
  Haemolysin = NA,
  Lipase = NA,
  Serin_Protease = NA,
  Nuclease = NA,
  TET_A = 100,   # Resistance genes, set as NA for Virulence
  TET_B = 0,
  AMP_C = 100,
  "blaCTX-M" = 100,
  "bla-SHV" = 100,
  "bla-TEM" = 0,
  Intergerons1 = 0,
  Sul = 0
)

# Add max and min for the chart scaling (for both virulence and resistance)
max_min_data <- data.frame(
  Aerolysin = c(100, 0),
  Elastase = c(100, 0),
  Haemolysin = c(100, 0),
  Lipase = c(100, 0),
  Serin_Protease = c(100, 0),
  Nuclease = c(100, 0),
  TET_A = c(100, 0),
  TET_B = c(100, 0),
  AMP_C = c(100, 0),
  "blaCTX-M" = c(100, 0),
  "bla-SHV" = c(100, 0),
  "bla-TEM" = c(100, 0),
  Intergerons1 = c(100, 0),
  Sul = c(100, 0)
)

# Combine the data with the max-min values for scaling
data_radar <- rbind(max_min_data, virulence_data, resistance_data)

# Set up the radar chart
par(mar = c(3, 3, 3, 3))  # Adjust margins

# Plot the radar chart
radarchart(
  data_radar, 
  axistype = 1,
  pcol = c("blue", "green"),  # Line colors: blue for virulence, green for resistance
  pfcol = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)),  # Fill colors for each
  plwd = 2,  # Line width
  cglcol = "grey", cglty = 1, axislabcol = "black", caxislabels = seq(0, 100, 25), cglwd = 0.8,
  vlcex = 0.8
)
# Add a title
title(main = "Comparing Virulence and Resistance Genes in A. dhakensis")

#Add a legend

legend(x = "topright", legend = c("Virulence genes", "Resistance genes"), 
       fill = c(rgb(0.2, 0.5, 0.5, 0.5), rgb(0.8, 0.2, 0.5, 0.5)), cex = 0.8)
```











