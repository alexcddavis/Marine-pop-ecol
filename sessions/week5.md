---
layout: single
author_profile: false
title: "Introduction to R"
#header:
    #og_image: /assets/images/cross-val-logo-v4.jpg
    #overlay_image: /assets/images/joel-filipe-small-warmer.jpg
    #caption: "Photo by [Joel Filipe](https://unsplash.com/@joelfilip) on [Unsplash](https://unsplash.com)"
classes: wide

sidebar:
  nav: "sessions"

---

## Week 5

**ZOOM LINK:** [https://ualberta-ca.zoom.us/j/97755262261](https://ualberta-ca.zoom.us/j/97755262261)

Well, you made it! This is the last session of the workshop series. We would very much have liked to do this workshop especially in person, as getting feedback/help in person is by far more useful. However, it wasn’t to be for us this year, so we’ll be offering this final exercise work-sheet as a remote delivery.

You will have received a dataset that goes along with this set of questions. This is a novel dataset that we haven’t worked with yet in previous sessions. Using this dataset, you can walk through the below questions that will let you apply what you’ve learned in class to somewhat novel problems. Obviously there is no requirement that you do this, but practicing coding in R is the only way you will truly learn the language. To help you through this set of questions, our live session on Nov. 04 will be a drop-in help session. We encourage you to get started on these questions as soon as you can after Session 4 on plotting is wrapped up.

Below are the questions as well as a set of answers that don’t tell you how to do the problem, but do let you check if you’re on the right track. Once you think you’ve completed the question, check your answer against the answer key. Set yourself a frustration threshold, and if you cannot get the right answer, only work on the problem until you’ve reached your threshold. If you can’t get the problem (some of them are meant to be tricky, because a lot of real-world data problems ARE tricky), then bring your problem to the live session next week and both Cole & Emma will be available to help you.

By Sunday, Nov. 08, there will be a series of videos posted here on the website which walk you through how to do each question in detail. We encourage you to try all the problems yourself beforehand, and then use the videos to either double check your approach or if you couldn’t solve the problem.

You can also reach out to us via the [contact](/Contact/) tab and we can try to help you via email.

Good luck, and thanks for a great series!

  **Question 1. Perform basic data manipulation tasks.**

  Note that we didn’t go over how to rename columns in our session on data management, as we already had a lot to cover, but this is a common task. We’ll briefly cover it here, but this is also a very google-able problem. To rename a column, we use the a familiar structure. The following function will do the trick:

 `names(DATAFRAME_NAME)[names(DATAFRAME_NAME) == “OLD_NAME”] = “NEW_NAME”`

 This is calling the function names() which returns a vector of the names of the dataframe. Here we’re going into that vector, finding where it is equal to the value we’re looking for, and replacing it with our new value.

 Now onto the question. Each subpart of the question will tell you to do some small data management or manipulation task. Perform them in order, and pay special attention to the specifics of names.

  a) Load the dataset into R and call it ‘final_df’

  b) Rename the columns as follows:

    `State.Province` → `state_province`
    `temp..C` → `temp_C`
    `dia..cm.` → `diam_cm`
    `ht.cm.` → `ht_cm`
    `total..g.` → `total_g`
    `gonad.vol..ml.` → `gonad_vol_ml`
    `gonad.wt..g.` → `gonad_wt_g`
    `food.vol..ml.` → `food_vol_ml`
    `jaw.cm` → `jaw_cm`

  **NOTE**: it is **bad** practice to include variables whose names have both capitals as the first letter, and no capitals in the first letter. However, you will come across much more egregious sins in other people’s data. We have neglected to change them all to one type, as it is common you will work with datasets that do not follow best practices.

  c) What is the data type of the 4th and 7th columns respectively?

  d) Make a new dataframe with only the first 6 rows of ‘final_df’ and call it `subset_final`. What are the dimensions (number of rows and columns) of `subset_final`

  e) How many entries are in ‘final_df’? (hint: an entry is the content of a single cell in a dataframe)

  f) What is the value of the cell in the 13th column in the 38th row?

  **Question 2. Clean data and remove obvious outliers**

  Here, we will follow a series of data manipulation steps, including making a new column and using our domain knowledge to remove outliers. A reminder that removing outliers is bad practice when those outliers constitute real data. However, thinking critically about the data at hand can allow us to remove values that have no possible place in biological reality, and thus can only occur as a result of human error. It is almost always best practice to remove values we know are erroneous on the part of the human collecting the data.

  a) Create a new empty column in the dataframe called `gonad_mass_ratio`

  b) There are some observations in the dataframe where either `total_g` or `gonad_wt_g` or both were not recorded. Remove these records.

  c) Calculate the ratio for gonad mass/total mass. Use the `gonad_wt_g` and the `total_g` columns, and store the ratio for each individual in the `gonad_mass_ratio` column.

  d) Generate a simple histogram plot in base R to identify outliers. Recall that since we’re calculating the ratio of the mass of the gonad to the total mass of the organism, the ratio should always be <1.0. The gonad, a subset of the whole organism, cannot weigh more than the total organism. Therefore, we can assume any values larger than 1.0 are some sort of error. It’s best we exclude them.

  e) Subset data to remove the outlier(s) from the data.

  **Question 3. Write a function called `get_mean_size()`to calculate the mean total mass of the urchins of a particular species in particular state or province:**

  - This function should have arguments for the state/province, the species, and the dataframe to perform the function on

  - The function should subset the original dataframe based on the state/province and species arguments given

  - The function should return the mean `total_g` column for the subset dataframe

  **Question 4. Create a dataframe called ‘loop_df’ that lists the mean total mass of the urchins of each species in each state/province.**

  **NOTE**: This is the hardest question in this exercise set! Don’t be discouraged if the answer eludes you at first. The goal here is to get you thinking like a programmer and solving problems you may not have considered before, and so we are trying to push you out of your comfort zone a little bit. Embrace it, challenges are fun.

  To do this, build a nested for loop to populate a matrix with the mean mass for each species and each province/state, and then change the matrix into a dataframe. Make use of your function from the last question. For this question you will write a nested for loop (that is, a loop within a loop) that will populate a matrix via each iteration of the loop. A more detailed outline of the problem follows:

  - Initialize a matrix with the same number of rows as the number of species, and the same number of columns as the number of states/provinces-- NOTE: this is a good way to speed up for loops by pre-generating your data structure outside the loop

  - Check that column `state_province` is of type character and column `Species` is of type character

  - Write a for loop to find each unique combination of column `state_province` and column `Species`. Make use of your function from the last question to calculate the mean mass (`total_g`) each unique combination, and put each value at the correct location in the matrix.

  - When building the matrix, ensure the species are the row values and the states/provinces are the column values

  - *HINT*: think **carefully** about how you want to achieve this before you start actually coding it. Solve the problem by first solving the domain problem using normal words and writing pseudocode, as is given here in the skeleton of the for loop, then try to code it. That is to say, it is good practice to break up the problem into domain-specific and computer-specific components. Think critically and identify what you want the answer to produce and the broad steps required to achieve that without worrying about the programming specifics. Then, translate your general answer into a code-specific answer. While this may seem redundant, it will help you immensely.

          for each unique value in column C {
              For each unique value in column D {

                Use function from question 2) to populate matrix

              }
            }

  - Turn the resulting matrix into a dataframe with the row names as the species names and the column names as the state/province names

  **NOTE**: while writing a for loop may not be the optimal way of performing this particular operation in R, populating a matrix or vector inside some sort of loop structure is a common programming task that you should know how to do. The interested reader is encouraged to check out the documentation on the `apply()` functions in R for the most efficient looping behavior in R. However, note that for loops are nearly ubiquitous in programming and all lower-level languages (C#, C++, Java etc.) and the majority of higher-level languages (Python, Julia, Ruby etc.) use for loops.

  **Question 5. Plot your data! Create a point and line plot showing the mean mass of the urchins throughout the years in the dataset.**

  Here, what you will do is plot the average mass on the y-axis versus the year on the x-axis.

  To get you started, we’ve written the code for you to create a summarized dataframe that has only the variables `year`, `Country`, `state_province`, and `Species`, along with a variable we created: `mean_mass` which is the mean mass from the `total_g` column.

                    summarized_data = do.call(rbind, by(final_df,
                                                          final_df[, c('year', 'Country', 'state_province', 'Species')],
                                        function(x) cbind(x[1, c('year', 'Country', 'state_province', 'Species')],
                                                          mean_mass = mean(x$total_g, na.rm = TRUE))))

  Copy and paste this code into your script and run it ahead of doing anything else. This code will only work if you’ve named the dataframe (final_df) and the columns as we’ve noted above. Do not worry too much about what the specific parts of this code are doing, unfortunately it is slightly beyond the scope of these workshops. Just know that if you have done your data cleaning properly, it will result in a dataframe (called `summarized_data`) that has 47 rows and 5 variables. For the interested reader, it is suggested you take the time to walk through the code and try and figure out what each part is doing with help from the documentation.

  Plot only the data for the species S. purpuratus in the country USA. (HINT: You’ll have to subset your dataframe `summarized_data` to do this.)

  Include the following components in your plot:

  - Separate the data by coloring two lines and the two sets of points according to the value of variable `state_province`
    - Colour ‘California’ blue and ‘Oregon’ green

  - Employ the `theme_bw()` theme to make the plot look more professional

  - Label your x-axis “Sampling Year”, your y-axis “Mass of Organisms”, and the title “Mean Yearly Mass for all S. purpuratus Sampled in the USA”

  - Include a legend for the colours, with the legend title “State”

  *BONUS:*

  If you want, try and re-create the plot above, but do it using a function that takes an argument for the country and the species to use in the plot. *EXTRA BONUS*: If you’re feeling **super** adventurous, try and see if you can alter your plotting code such that the label of the country and the species name in the title of the plot change along with the arguments of the function.

# Answers Videos

## Question 1
{% include video id="cU5qKuJ_Yg8" provider="youtube" %}
## Question 2
{% include video id="kwXKAv4sbcw" provider="youtube" %}
## Question 3
{% include video id="VQnjmnY-isc" provider="youtube" %}
## Question 4
{% include video id="PJY-gEESFHc" provider="youtube" %}
## Question 5
{% include video id="IF8ubu_8B1k" provider="youtube" %}
## Bonus Question
{% include video id="eU1tvC_yDhA" provider="youtube" %}
