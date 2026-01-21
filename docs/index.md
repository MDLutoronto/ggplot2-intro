---
title: "Introduction to GGPLOT2"
layout: "home"
description: ""
permalink: "/"  #! Remove this if not the homepage
---

# Introduction to GGPLOT2

 This guide introduces users to the ggplot2 R package. Ggplot2 is a popular package that is used to make publication quality graphs in R. The official documentation for the ggplot2 package can be found [here](https://cran.r-project.org/web/packages/ggplot2/ggplot2.pdf). It includes descriptions of functions and sample datasets.

This guide consists of 3 data visualization examples. You can download the code used in this guide [here](https://maps.library.utoronto.ca/workshops/ggplot2/codeworkshop.php).

Once you have gone over these examples and you feel confident about them, you can test your understanding by trying this [activity](https://maps.library.utoronto.ca/workshops/ggplot2/activity.php). If you have any questions, you can request for assistance by filling out our support request form [here](https://mdl.library.utoronto.ca/about/contact-form).

Install package
---------------

```
install.packages("ggplot2")
library(ggplot2

```

Example 1: Histogram of the Price of Diamonds
---------------------------------------------

```
data(diamonds)
ggplot(diamonds, aes(price)) + geom_histogram()
ggplot(diamonds, aes(price)) + geom_histogram() + theme_classic()
ggplot(diamonds, aes(price)) + geom_histogram(binwidth=100) + theme_classic()
ggplot(diamonds, aes(price)) + 
  geom_histogram(binwidth=100, fill="darkblue", color="lightblue") + 
  theme_classic() + 
  ggtitle("Histogram of the Price of Diamonds") + 
  theme(plot.title=element_text(size=20, hjust=0.5)) + 
  xlab("Price") + ylab("Count")
ggsave("histogram1.png")

```
![Histogram of Price of Diamonds]({{ '/assets/images/Example1.png' | relative_url }})

 

Example 2: Scatterplot of the Price and the Weight of Diamonds
--------------------------------------------------------------

```
ggplot(diamonds, aes(carat, price)) + geom_point()
ggplot(diamonds, aes(carat, price, colour=clarity)) + 
  geom_point(shape="diamond filled") + 
  theme_light() + 
  ggtitle("Relationship between the Price and the Weight of Diamonds")

```

```
install.packages("colourpicker")
myscattercolours <- c("#7FFFD4", "#66CDAA", "#458B74", "#00FFFF", "#1C86EE", "#104E8B", "#8B4500", "#FF7F00")

```

```
ggplot(diamonds, aes(carat, price, colour=clarity)) + 
  geom_point(shape="diamond filled") + 
  theme_light() + 
  ggtitle("Relationship between the Price and the Weight of Diamonds") + 
  scale_colour_manual(values=myscattercolours) +
  xlab("Carat") + ylab("Price") + 
  guides(colour=guide_legend("Clarity"))

```
![Scatterplot of the Price and the Weight of Diamonds]({{ '/assets/images/Example2.png' | relative_url }})

 

Example 3: Time Series of Median Unemployment Duration in Weeks
---------------------------------------------------------------

```
data(economics)
ggplot(economics, aes(x=date, y=uempmed)) +
  theme_minimal() +
  geom_line(colour="yellow3", linewidth=1) + 
  labs(title="US Economic Time Series",
       subtitle="Median Unemployment Duration vs Month of Data Collection") +
  xlab("Month of Data Collection") +
  ylab("Median Unemployment Duration in Weeks")

```
![Time Series of Median Unemployment Duration in Weeks]({{ '/assets/images/Example3.png' | relative_url }})

 

Resources
---------

1\. GGPLOT2 Documentation: [https://cran.r\-project.org/web/packages/ggplot2/ggplot2\.pdf](https://cran.r-project.org/web/packages/ggplot2/ggplot2.pdf)  
2\. GGPLOT2 Tidyverse Reference: [https://ggplot2\.tidyverse.org/reference/](https://ggplot2.tidyverse.org/reference/)  
3\. Additional code [here](https://maps.library.utoronto.ca/workshops/ggplot2/codeactivity.php).

 

Technique: [Data Visualization](/technique/data-visualization) \| Tools: [R](/tools/r-0)**Date Created:** 2023\-07\-12**Updated:** 2023\-11\-06
