Download Link: https://assignmentchef.com/product/solved-r-midterm-exam
<br>
<h1>Question 1</h1>

<ol>

 <li>Consider code chunk <strong>Q1</strong> and give the resulting output from the following R commands (or the resulting error if one is produced):

  <ol>

   <li>my_Costco_list[2]</li>

   <li>my_Costco_list[[1]][2]</li>

  </ol></li>

</ol>

<ul>

 <li>my_Costco_list[[1]][2,2]</li>

</ul>

<ol>

 <li>Consider code chunk <strong>Q1</strong> and answer the following multiple choice questions (please list all that apply for each question):

  <ol>

   <li>Which of the following commands returns the result “Coffee”?</li>

   <li>The class of the object returned by both_lists[2] is a</li>

  </ol></li>

</ol>

<ul>

 <li>The class of the object returned by both_lists[[2]]$Location is a</li>

</ul>

<ol>

 <li>Consider code chunk <strong>Q1</strong> for the following questions:

  <ol>

   <li>Write a line of code that will change the Location column of the tibble in my_Costco_list to an ordered factor where the order of the levels is in the following order: Clothes, Cereal, Refrigerated.</li>

   <li>Write a line of code using your answer to part (i) to compute the <strong>minimum</strong> amount of items (not the number of different items) required in each location.</li>

  </ol></li>

</ol>

<h1>Question 2</h1>

<ol>

 <li><strong>[15 marks]</strong> Please indicate which plot <strong>best</strong> summarizes the characeristic the characteristic (the name of the plot, not the function):</li>

</ol>

<ol>

 <li>Which plot best allows one to identify points that are <strong>outliers</strong> (i.e. far from the central location the data): A: Boxplot B: Histogram?</li>

 <li>Which plot best allows one to assess the <strong>skew</strong> of the data: A: Boxplot B: Histogram?</li>

</ol>

<ul>

 <li>Which plot should be used to summarize the distribution of quantitative data that take on a large number of unique values: A: Histogram B: Barplot?</li>

</ul>

<ol>

 <li>Which plot should be used to summarize the counts from different levels of a qualitative factor variable: A: Histogram B: Barplot?</li>

 <li>If we want to compare the central 50% of the values of a quantiative variable across multiple levels of a separate qualitative variable, which plot should be used:

  <ol>

   <li>One boxplot for each group in the same plot</li>

   <li>One boxplot for each group in a different plot</li>

   <li>One hisotogram for each group in the same plot</li>

   <li>One histogram for each group in a different plot?</li>

  </ol></li>

</ol>

Answer the parts (b), (c), and (d) below based on a dataset from Kaggle containing the prices of Hass avocados over a period of over three years. The original dataset is used in the book “Introduction to Data Analysis” and is available through the aida package in R (which you can install to access the data).

<em>### You can install the aida package via: </em>

<em>### install.packages(“remotes”) ### remotes::install_github(“michael-franke/aida-package”)</em>

<strong>library</strong>(aida) glimpse(data_avocado)

Rows: 18,249

Columns: 7

$ Date              &lt;date&gt; 2015-12-27, 2015-12-20, 2015-12-13, 2015-12-06, 201…

$ average_price     &lt;dbl&gt; 1.33, 1.35, 0.93, 1.08, 1.28, 1.26, 0.99, 0.98, 1.02…

$ total_volume_sold &lt;dbl&gt; 64236.62, 54876.98, 118220.22, 78992.15, 51039.60, 5…

$ small             &lt;dbl&gt; 1036.74, 674.28, 794.70, 1132.00, 941.48, 1184.27, 1…

$ medium            &lt;dbl&gt; 54454.85, 44638.81, 109149.67, 71976.41, 43838.39, 4…

$ large             &lt;dbl&gt; 48.16, 58.33, 130.50, 72.58, 75.78, 43.61, 93.26, 80… $ type              &lt;chr&gt; “conventional”, “conventional”, “conventional”, “con…

data_avocado %&gt;% arrange(Date) %&gt;% head(.) %&gt;% kable(.) %&gt;% kable_styling()

<table width="736">

 <tbody>

  <tr>

   <td width="110"><strong>Date</strong></td>

   <td colspan="2" width="122"><strong>average_price</strong></td>

   <td colspan="2" width="148"><strong>total_volume_sold</strong></td>

   <td colspan="3" width="99"><strong>small</strong></td>

   <td colspan="2" width="107"><strong>medium</strong></td>

   <td width="54"><strong>large</strong></td>

   <td width="96"><strong>type</strong></td>

  </tr>

  <tr>

   <td width="110">2015-01-04</td>

   <td colspan="2" width="122">1.22</td>

   <td colspan="2" width="148">40873.28</td>

   <td colspan="3" width="99">2819.50</td>

   <td colspan="2" width="107">28287.42</td>

   <td width="54">49.90</td>

   <td width="96">conventional</td>

  </tr>

  <tr>

   <td width="110">2015-01-04</td>

   <td colspan="2" width="122">1.00</td>

   <td colspan="2" width="148">435021.49</td>

   <td colspan="3" width="99">364302.39</td>

   <td colspan="2" width="107">23821.16</td>

   <td width="54">82.15</td>

   <td width="96">conventional</td>

  </tr>

  <tr>

   <td colspan="2" width="181">2015-01-04</td>

   <td colspan="2" width="109">1.08</td>

   <td colspan="2" width="99">788025.06</td>

   <td width="82">53987.31</td>

   <td colspan="2" width="90">552906.04</td>

   <td colspan="2" width="79">39995.03</td>

   <td width="96">conventional</td>

  </tr>

  <tr>

   <td colspan="2" width="181">2015-01-04</td>

   <td colspan="2" width="109">1.01</td>

   <td colspan="2" width="99">80034.32</td>

   <td width="82">44562.12</td>

   <td colspan="2" width="90">24964.23</td>

   <td colspan="2" width="79">2752.35</td>

   <td width="96">conventional</td>

  </tr>

  <tr>

   <td colspan="2" width="181">2015-01-04</td>

   <td colspan="2" width="109">1.02</td>

   <td colspan="2" width="99">491738.00</td>

   <td width="82">7193.87</td>

   <td colspan="2" width="90">396752.18</td>

   <td colspan="2" width="79">128.82</td>

   <td width="96">conventional</td>

  </tr>

  <tr>

   <td width="110"></td>

   <td width="71"></td>

   <td width="50"></td>

   <td width="58"></td>

   <td width="90"></td>

   <td width="8"></td>

   <td width="82"></td>

   <td width="8"></td>

   <td width="82"></td>

   <td width="25"></td>

   <td width="54"></td>

   <td width="96"></td>

  </tr>

 </tbody>

</table>

2015-01-04                           1.40                    116253.44          3267.97       55693.04                                           109.55                 conventional

Each row in the dataset contains information on the price and volume (in pounds) of avocados sold from one outlet on a particular date for a particular type of avocado (organic or conventional). The variables in the data set for each outlet one each date are as follows:

<ol>

 <li>Figure 1 shows three different panels examining the relationship between average price and type of avocado.

  <ol>

   <li>Compare the distributions of the average prices for the conventional and organic avocados. In particular, compare their central locations, spreads and skew to conclude whether there is evidence in this data that the average prices of organic avocados is different from those of conventional avocados.</li>

   <li>The lines in the center of the boxes in Panel (a) indicate the value of a summary statistic of the daily outlet average prices for each of the two types of avocado in the dataset.</li>

  </ol></li>

</ol>

Write a function that will use the data_avocado object to compute these two values and return them in a tibble with one column for the type and the other with the summary statistic.

<ul>

 <li>Explain what was changed or added to the code to yield the different figures for (b) and panel (c). In particular, explain why the bars look different in the two plots and why the y-axis scales of the figures are different.</li>

</ul>

<ol>

 <li>Figure 2 shows two different panels comparing how the total volume sold of conventional avocados change over time (note that both plots are plotted on a log scale).

  <ol>

   <li>Which of the two panels, (a) or (b), best shows the pattern of total volume sold?</li>

  </ol></li>

</ol>

Explain your answer.

<ol>

 <li>Would a 2D histogram make sense to use for summarizing this particular relationship? Briefly explain why or why not.</li>

</ol>

<ul>

 <li>Below is the line of code that generated the plot in panel (b). Change the line of code below so that it produces a pair plots that contains total_volume_sold for <strong>both</strong> conventional and organic <strong>separately</strong> over time (i.e. in different plotting areas of the same plot). s</li>

</ul>

ggplot(data_avocado %&gt;% filter(type==”conventional”),            aes(x=Date,y=total_volume_sold,group=Date)) +   geom_boxplot() + ggtitle(“Panel (b)”)+ scale_y_log10()

Why can’t you use the original data_avocado data object to plot the total volume sold by the size of the avocados using the same figure you gave code to generate in part (iii) above? Explain why and then write a line of code which would allow you to generate the necessary data object which could then be used to make such a plot (you don’t need to include the code for the plot).