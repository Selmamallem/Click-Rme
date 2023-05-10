# Click-Rme

## Presentation
The presentation is untitled "Refugee flows and  state contributions to peacekeeping missions". The presentation was created in R-markdown under xaringan r markdown as part of a class homework. The data was extracted from a project done by The Data was collected from scholar Dr. Gary Uzonyi, Department of Political Science, University of Massachusetts Lowell, in  his research paper, " Refugee flows and state contributions to post-Cold War UN peacekeeping missions," Journal of Peace Research 2015, Vol. 52(6) 743–757.

## Data
The data explores the current understanding of UN peacekeeping troop contributions focusing on two aspects: 

- Which states participate in missions. 
- Which conflicts states send their troops to and the size of contributions they are willing to provide. 

## Presentation slides
The presentation slides include respectively: 
- **Title slide** with topic and author info **mentioned before**.
- **Data:** Description of the data.
- **Analysis 1:** Description of the data on a key variable.
- **Analysis 2:** Description of the data on second variable in addition to a group comparison. 

## Where to find data?
The data can be found in: https://www.jstor.org/stable/24557464
## Main packages used :shipit:
The main packages that were needed were: 
- [ ] *tidyverse* 
- [ ] *patchwork* 
- [ ] *ggplot2* 
- [ ] *xaringanthemer* 
- [ ] *dplyr* :tada:

## Code Chunk: Plotting
The following code is for visualizing different data. The purpose of this code is to help users create a map for whatever data they have that contains US states. 
**Packages to download:** 
```python
library(dplyr)
library(usmap)
library(ggplot2)
library(readr)
```
Upload any data you have, the data I used was from class. 

```python
covid <- covid %>% drop_na()

covidcc <- covid %>% group_by(state)%>%
  summarise(count = n())%>%
  arrange(desc(count))

ggplot(covidcc, aes(x = state, y = count)) +
  geom_bar(stat = "identity", fill = "orange") +
  scale_x_discrete(labels = c("Alabama", "Alaska", "Arizona", "Arkansas", "California", "Colorado", "Connecticut", "Delaware", "Florida", "Georgia", "Hawaii", "Idaho", "Illinois", "Indiana", "Iowa", "Kansas", "Kentucky", "Louisiana", "Maine", "Maryland", "Massachusetts", "Michigan", "Minnesota", "Mississippi", "Missouri", "Montana", "Nebraska", "Nevada", "New Hampshire", "New Jersey", "New Mexico", "New York", "North Carolina", "North Dakota", "Ohio", "Oklahoma", "Oregon", "Pennsylvania", "Rhode Island", "South Carolina", "South Dakota", "Tennessee", "Texas", "Utah", "Vermont", "Virginia", "Washington", "West Virginia", "Wisconsin", "Wyoming"))+
  theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1)) +
  labs(x = "state", y = "Number of Cases", title = "COVID-19 Cases by state")
  ```



