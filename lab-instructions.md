::page{title=""}

## Creating Data Visualizations using ggplot

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0105EN-SkillsNetwork/labs/Module2/images/SN_web_lightmode.png">
</br>
</br>
</br>

**Objective for Exercise**

We will create different data visualizations using the `ggplot` package using the inbuilt dataset in R called `mtcars`

1. Click on the `+` symbol on the top left and choose `R Script` from the menu to open a new R edit window in RStudio:

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0105EN-SkillsNetwork/labs/Module2/images/22-DS0105EN-2.png" width="600">

2. Read and view the first 5 rows of the Data using the following:

```
library(datasets)

#Load Data

data(mtcars)

#View first 5 rows

head(mtcars, 5)
```

3. Type this `?mtcars` to get information about the variables. This will print the information at the bottom right panel, on the `Help` tab

4. Copy and paste the following code to load the `ggplot` package and create a scatterplot of `disp` and `mpg`.

```
#load ggplot package
library(ggplot2)

#create a scatterplot of displacement (disp) and miles per gallon (mpg)

ggplot(aes(x=disp,y=mpg,),data=mtcars)+geom_point()
```

5. Use the following code to add a title.

```

#Add a title

ggplot(aes(x=disp,y=mpg,),data=mtcars)+geom_point()+ggtitle("displacement vs miles per gallon")
```

6. Use the following code to change the name of the `x-axis` and `y-axis`

```

#change axis name

ggplot(aes(x=disp,y=mpg,),data=mtcars)+geom_point()+ggtitle("displacement vs miles per gallon") + labs(x = "Displacement", y = "Miles per Gallon")
```

7. Use the following to create a boxplot of the the distribution of `mpg` for the individual Engine types `vs Engine (0 = V-shaped, 1 = straight)`
To do this you have to make `vs` a string or factor.

```
#make vs a factor
mtcars$vs <- as.factor(mtcars$vs)

#create boxplot of the distribution for v-shaped and straight Engine

ggplot(aes(x=vs, y=mpg), data = mtcars) + geom_boxplot()
```

8. Add color to the boxplots to help differentiate:

```
ggplot(aes(x=vs, y=mpg, fill = vs), data = mtcars) + 
  geom_boxplot(alpha=0.3) +
  theme(legend.position="none")
```

9. Finally, let us create the histogram of weight `wt`.

```
ggplot(aes(x=wt),data=mtcars) + geom_histogram(binwidth=0.5)
```

This concludes this lab, we hope that you had fun!

## Author(s)

[Aije Egwaikhide](https://www.linkedin.com/in/aije-egwaikhide/)

<!-- ## Change log

| Date | Version | Changed by | Change Description |
|------|--------|--------|---------|
| 2023-05-04 | 1.1 | Benny | Added page numbers and republished|
| 2020-12-14 | 1.0 | Aije | Created initial version of the lab| -->

<footer><img align="left" src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-RP0321EN-SkillsNetwork/footer_logo_sn_ibm.png" alt="cognitiveclass.ai logo"> </footer>

