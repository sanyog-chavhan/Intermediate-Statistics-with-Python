
# Exploring Intermediate Statistics with Python

This repository hosts a Google Colab notebook aimed at providing a hands-on introduction to fundamental statistical concepts using Python. Through a real dataset and clear explanations, it'll guide you through key measures like Normal Distribution, Standard Error of the Mean, P-value, Confidence Interval, Shapiro Wilks Test, T-test, and Chi-square Test.

## Table of Contents

1. [Dataset Description](#dataset-description)
2. [Exploring Statistical Concepts](#exploring-statistical-concepts)
3. [How to Use the Notebook](#how-to-use-the-notebook)

## Dataset Description

The dataset used is the Wine Quality dataset which includes different wine features like:

    fixed acidity	
    volatile acidity	
    citric acid
    residual sugar
    chlorides
    free sulfur dioxide
    total sulfur dioxide
    density	pH
    sulphates
    alcohol	quality

The dataset used to explain T-test and Chi-square test is the Stackoverflow dataset which includes different features like:

    Country	Salary	
    YearsCodedJob
    OpenSource
    Hobby
    CompanySizeNumber
    Remote
    CareerSatisfaction
    Data_scientist
    Database_administrator
    Developer_with_stats_math_background	
    DevOps
    Embedded_developer
    Graphic_designer
    Graphics_programming
    Machine_learning_specialist
    Mobile_developer
    Quality_assurance_engineer
    Systems_administrator
    Web_developer

## Exploring Statistical Concepts

### Normal Distribution

Normal Distribution aka Gaussian Distribution is a common probability distribution that forms a **bell-shaped curve** when plotted. It's characterized by its symmetry around the mean, with most values clustering around the mean and fewer values farther away.

This is very essential in statistics as many real-world phenomena tend to follow this distribution making it fundamental in data analysis.

For example,

Imagine you're measuring the heights of a large group of people. If you were to plot the heights on a graph, you might find that most people have heights close to the average height, while very tall or very short individuals are less common. This clustering around the average height is a characteristic of the Normal Distribution.

The **68-95-99 rule** is a guideline that applies to data that follows a Normal Distribution:

Approximately **68%** of the data falls within one standard deviation (σ) of the mean (μ).

    This can be expressed as: μ - σ ≤ x ≤ μ + σ

Approximately **95%** falls within two standard deviations from the mean.

    This can be expressed as: μ - 2σ ≤ x ≤ μ + 2σ

About **99.7%** falls within three standard deviations from the mean.

    This can be expressed as: μ - 3σ ≤ x ≤ μ + 3σ    

### P-value

Before proceeding with Shapiro Wilks Test, let's talk about P-value and Hypothesis testing and terms like Null Hypothesis and Alternative Hypothesis and why P-value is essential during Shapiro Wilks Test

A p-value is a number that helps us decide whether the evidence we have **supports a hypothesis or if it's just due to chance**. A low p-value suggests strong evidence against the "nothing special" idea (null hypothesis), while a high p-value means the evidence isn't strong enough to reject that idea.

In Layman's terms, imagine you're in a courtroom trial. The p-value is like the evidence presented in court against a defendant (hypothesis). It tells you how strong the evidence is against your hypothesis. If the p-value is small, it suggests the evidence is strong, and you might consider the hypothesis not true.

**Null Hypothesis (H₀)**: This is like assuming nothing unusual is happening. It's the default idea that there's no effect or difference. For example, in a trial, the null hypothesis might be **"the defendant is innocent."**

**Alternative Hypothesis (H₁ or Ha)**: This is like suggesting something is different or interesting. It's the opposite of the null hypothesis. In the trial, the alternative hypothesis might be **"the defendant is guilty."**

A threshold value is required for decision-making in such cases where we're presented with a Null hypothesis and an Alternative hypothesis. Think of a p-value threshold as your courtroom rule.

**For every hypothesis, there is an alternative hypothesis.**

For example,

Null Hypothesis (H0): Average salary of a Cloud Engineer is $80k.

The alternative hypothesis for this will be,

Alternative Hypothesis (H1): Average salary of a Cloud Engineer is not $80k.

Let's say the **threshold is 0.05** in this case, so if the **P-value is small than the threshold, we'd reject the null hypothesis** in favour of the alternative hypothesis(**Average salary of a Cloud Engineer is not $80k**).

Else if the **P-value is bigger than the threshold, we'd accept the null hypothesis**(**Average salary of a Cloud Engineer is $80k**).

### Shapiro Wilks Test

Shapiro Wilks Test was created in 1965 **in order to check the normality.**

At its core, the Shapiro-Wilk test **assesses the null hypothesis that your data follows a normal distribution**. The test generates a p-value, which helps you make an informed decision about whether you can comfortably assume that your data comes from a normal distribution.

**Null Hypothesis (H₀)**: The null hypothesis assumes that your data follows a normal distribution.

**Alternative Hypothesis (H₁)**: The alternative hypothesis assumes that your data doesn't follow a normal distribution.

Let's consider the threshold as 0.05 in this case,

**If P-value < 0.05 = Rejecting the Null Hypothesis (The assumption that the data follows a normal distribution is rejected)**

**If P-value > 0.05 = Accepting the Null Hypothesis (The assumption that the data follows a normal distribution is accepted)**

### Standard Error of the mean

**Standard Error of the Mean (SEM)** is like a measure of how much your sample mean might wiggle around from the true population mean. **It gives you an idea of how reliable your sample mean is as an estimate of the actual average.**

In simple terms, **SEM tells you how much you can trust your calculated average from your sample to represent the whole group.**

Let's say you're a scientist studying the heights of sunflowers in a field. You measure the heights of 20 sunflowers and find the average height to be 120 cm.

But wait! Your sample of 20 sunflowers might not represent all the sunflowers in the field perfectly. Some sunflowers might be taller, some might be shorter, and your sample could be a bit lucky or unlucky in terms of height.

This is where SEM comes in. Let's say you calculate the SEM to be 5 cm. It means that you can be reasonably confident that the true average height of all the sunflowers in the field is likely to fall within 115 cm to 125 cm (120 ± 5).

    SEM =  SampleSize/√SampleStandardDeviation

### Confidence Interval

Let's talk about Confidence Interval and Confidence Level and why they are necessary while estimation of different parameters.

In statistics, a confidence interval is a range of values around an estimated parameter that you're reasonably confident contains the true parameter value.

Mathematically, a confidence interval is typically represented as:

**Estimate ± Margin of Error**

Where:

**Estimate** is the calculated value based on your data, such as the **sample mean or proportion**.

**Margin of Error** accounts for the variability in your data and is determined by the chosen **confidence level and the variability of the data**.

The confidence level (often denoted as 1 - α) indicates the **probability** that your confidence interval contains the true parameter value.

For instance, **a 95% confidence level means you're 95% confident that the true parameter value lies within your interval**.

Read more about Confidence Interval here: https://towardsdatascience.com/confidence-intervals-explained-simply-for-data-scientists-8354a6e2266b

### T-test

The t-test calculates a **t-value based on the means and variability of your two groups**. Then, it compares this t-value to a critical t-value, which is like a benchmark for significance. If your calculated t-value is much bigger than the critical value, it suggests the differences are meaningful.

In layman's terms, **a t-test is like a detective tool for comparing two groups and figuring out if they're really different or if the differences could just be due to random chance**.

**T-test helps one understand whether one group is statistically different from the other**.

### Chi-square Test

The chi-square test calculates a **chi-square statistic based on the differences between your observed and expected counts** in a contingency table. Then, it compares this statistic to a critical chi-square value **to determine if the differences are significant**.

In Layman's terms, imagine you're curious if there's a connection between two categorical variables, like the color of cars and their popularity. The chi-square test is like a detective tool that helps you figure out if these variables are related or if any relationship you see could just be due to chance.

## How to Use the Notebook

Follow these steps to start exploring the statistical concepts using the provided Google Colab notebook:

1. **Clone or Download:** Clone this repository to your local machine using Git or download the repository as a ZIP file.

2. **Open in Google Colab:** If you're using Google Colab, you can directly open the notebook by clicking on the "Open in Colab" button at the top of the notebook file.

3. **Upload to Google Colab:** If you prefer to use Google Colab via your browser, upload the downloaded notebook (`notebook.ipynb`) and the CSV file to your Google Drive. Then, open it with Google Colab by right-clicking the file and selecting "Open with" > "Google Colaboratory".

4. **Interact with the Notebook:** Once the notebook is open, you can follow along with the code cells. Execute the code cells by clicking the "Run" button or using the keyboard shortcut (Shift + Enter).

5. **Explore and Learn:** Engage with the interactive exercises and explanations to grasp the concepts of mean, median, mode, correlation, and standard deviation.

Feel free to experiment, modify the code, and further explore statistical measures on your own!

