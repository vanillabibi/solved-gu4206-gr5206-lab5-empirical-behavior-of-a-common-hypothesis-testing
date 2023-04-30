Download Link: https://assignmentchef.com/product/solved-gu4206-gr5206-lab5-empirical-behavior-of-a-common-hypothesis-testing
<br>
Make sure that you upload the PDF (or HTML) output after you have knitted the file. The files you upload to the Canvas page should be updated with commands you provide to answer each of the questions below. You can edit this file directly to produce your final solutions.

<h1>Goal</h1>

The goal of this lab is to investigate the empirical behavior of a common hypothesis testing procedure through simulation using R. We consider the traditional two-sample t-test.

<h1>Two-Sample T-Test</h1>

Consider an experiment testing if a 35 year old male’s heart rate statistically differs between a control group and a dosage group. Let <em><sub>X </sub></em>denote the control group and let <em><sub>Y </sub></em>denote the drug group. One common method used to solve this problem is the two-sample t-test. The null hypothesis for this study is:

<em>H</em><sub>0 </sub>: <em>µ</em><sub>1 </sub><em>− µ</em><sub>2 </sub>= ∆<sub>0</sub><em>,</em>

where ∆<sub>0 </sub>is the hypothesized value. The assumptions of the two-sample t-test follow below:

<h2>Assumptions</h2>

<ol>

 <li><em><sub>X</sub></em><sub>1</sub><em><sub>,X</sub></em><sub>2</sub><em><sub>,…,Xm </sub></em>is a random sample from a normal distribution with mean <em><sub>µ</sub></em><sub>1 </sub>and variance <em><sub>σ</sub></em><sub>1</sub><sup>2</sup><em><sub>.</sub></em></li>

 <li><em><sub>Y</sub></em><sub>1</sub><em><sub>,Y</sub></em><sub>2</sub><em><sub>,…,Yn </sub></em>is a random sample from a normal distribution with mean <em><sub>µ</sub></em><sub>2 </sub>and variance <em><sub>σ</sub></em><sub>2</sub><sup>2</sup><em><sub>.</sub></em></li>

 <li>The <em><sub>X </sub></em>and <em><sub>Y </sub></em>samples are independent of one another.</li>

</ol>

<h2>Procedure</h2>

The test statistic is

<em>t</em><em>calc </em>= <em>x</em><u>¯</u>q<em>−</em><em>s</em><u>1</u>2<em>y</em><u>¯</u>+<em>− </em><u>∆</u><em>sn</em><u>2</u>20<em>,</em>

<em>m</em>

where <em><sub>x,</sub></em>¯ <em><sub>y</sub></em>¯ are the respective sample means and <em><sub>s</sub></em><sup>2</sup><sub>1</sub><em>,s</em><sup>2</sup><sub>2 </sub>are the respective sample standard deviations.

The approximate degrees of freedom is

<em>s</em><em><sub>m</sub></em>2<u>1 </u>+ <em>s</em>2<u>2</u>2 <em>df </em>=           <em><sub>n</sub></em>

<em>m−</em>1                     <em>n−</em>1

Under the null hypothesis, <em><sub>tcalc </sub></em>(or <em><sub>Tcalc</sub></em>) has a student’s t-distribution with <em><sub>df </sub></em>degrees of freedom.

<h2>Rejection rules</h2>

<table width="346">

 <tbody>

  <tr>

   <td width="220"> </td>

   <td width="126"> </td>

  </tr>

  <tr>

   <td width="220"><em>H<sub>A </sub></em>: <em>µ</em><sub>1 </sub><em>− µ</em><sub>2 </sub><em>&gt; </em>∆<sub>0                         </sub>(upper-tailed)</td>

   <td width="126"><em>P</em>(<em>t<sub>calc </sub>&gt; T</em>)</td>

  </tr>

  <tr>

   <td width="220"><em>H<sub>A </sub></em>: <em>µ</em><sub>1 </sub><em>− µ</em><sub>2 </sub><em>&lt; </em>∆<sub>0                          </sub>(lower-tailed)</td>

   <td width="126"><em>P</em>(<em>t<sub>calc </sub>&lt; T</em>)</td>

  </tr>

  <tr>

   <td width="220"><em>H<sub>A </sub></em>: <em>µ</em><sub>1 </sub><em>− µ</em><sub>2 </sub>= ∆<em>6         </em><sub>0              </sub>(two-tailed)</td>

   <td width="126">2 <em>∗ P</em>(<em>|t<sub>calc</sub>| &gt; T</em>)</td>

  </tr>

 </tbody>

</table>

Alternative Hypothesis                    P-value calculation

Reject <em><sub>H</sub></em><sub>0 </sub>when:

<em>Pvalue ≤ α</em>

<h1>Tasks</h1>

<ul>

 <li>Using the <strong><sub>R </sub></strong>function <strong><sub>test</sub></strong>, run the two sample t-test on the following simulated dataset. Note that the <strong><sub>t.test </sub></strong>function defaults a two-tailed alternative. Also briefly interpret the output.</li>

</ul>

<table width="632">

 <tbody>

  <tr>

   <td width="632"><strong>set.seed</strong>(5) sigma=5Control &lt;- <strong>rnorm</strong>(30,mean=10,sd=sigma)Dosage &lt;- <strong>rnorm</strong>(35,mean=12,sd=sigma)<em>#t.test()</em></td>

  </tr>

 </tbody>

</table>

<ul>

 <li>Write a function called <strong><sub>test.sim </sub></strong>that simulates <strong><sub>R </sub></strong>different samples of <em><sub>X </sub></em>for control and <strong><sub>R </sub></strong>different samples of <em><sub>Y </sub></em>for the drug group and computes the proportion of test statistics that fall in the rejection region. The function should include the following: • Inputs:

  <ul>

   <li><strong><sub>R </sub></strong>is the number of simulated data sets (simulated test statistics). Let <strong><sub>R </sub></strong>have default 10,000.</li>

   <li>Parameters <strong><sub>mu1</sub></strong>, <strong><sub>mu2</sub></strong>, <strong><sub>sigma1 </sub></strong>and <strong><sub>sigma2 </sub></strong>which are the respective true means and true standard deviations of <em><sub>X </sub></em>&amp; <em><sub>Y </sub></em>. Let the parameters have respective defaults <strong><sub>mu1=0</sub></strong>, <strong><sub>mu2=0</sub></strong>,</li>

  </ul></li>

</ul>

<strong>sigma1=1 </strong>and <strong>sigma2=1</strong>.

<ul>

 <li>Sample sizes <strong>n </strong>and <strong>m </strong>defaulted at <strong>m=n=30</strong>.</li>

 <li><strong><sub>level </sub></strong>is the significance level as a decimal with default at <em><sub>α </sub></em>= <em><sub>.</sub></em> <strong>– </strong><strong><sub>value </sub></strong>is the hypothesized value defaulted at 0.</li>

 <li>The output should be a <strong><sub>list </sub></strong>with the following labeled elements:</li>

 <li><strong><sub>list </sub></strong>vector of simulated t-statistics (this should have length <strong><sub>R</sub></strong>).</li>

 <li><strong><sub>list </sub></strong>vector of empirical p-values (this should have length <strong><sub>R</sub></strong>).</li>

 <li><strong><sub>rate </sub></strong>is a single number that represents the proportion of simulated test statistics that fell in the rejection region.</li>

</ul>

I started the function below:

<table width="632">

 <tbody>

  <tr>

   <td width="632">t.test.sim &lt;- <strong>function</strong>(R=10000, mu1=0,mu2=0, sigma1=1,sigma2=1, m=30,n=30, level=.05, value=0, direction=”Two”) {<em>#Define empty lists </em>statistic.list &lt;- <strong>rep</strong>(0,R) pvalue.list &lt;- <strong>rep</strong>(0,R)<em>#for (i in 1:R) {</em><em># Sample realized data</em><em>#Control &lt;-</em><em>#Dosage &lt;-</em><em># Testing values</em><em>#testing.procedure &lt;-</em><em>#statistic.list[i] &lt;-</em><em>#pvalue.list[i] &lt;-</em><em>#}</em><em>#rejection.rate &lt;-</em><em>#return()</em>}</td>

  </tr>

 </tbody>

</table>

Evaluate your function with the following inputs <strong>R=10</strong>,<strong>mu1=10</strong>,<strong>mu2=12</strong>,<strong>sigma1=5 </strong>and <strong>sigma2=5</strong>. 3) Assuming the null hypothesis

<em>H</em><sub>0 </sub>: <em>µ</em><sub>1 </sub><em>− µ</em><sub>2 </sub>= 0

is true, compute the empirical size (or rejection rate) using 10,000 simulated data sets. Use the function

<strong>t.test.sim </strong>to accomplish this task and store the object as <strong><sub>sim</sub></strong>. Output the empirical size quantity <strong>sim$rejection.rate</strong>. Comment on this value. What is it close to?

<strong>Note: </strong>use <strong>mu1=mu2=10 </strong>(i.e., the null is true). Also set <strong>sigma1=5</strong>,<strong>sigma2=5 </strong>and <strong>n=m=30</strong>.

<ul>

 <li>Plot a histogram of the simulated P-values, i.e., <strong><sub>hist(sim$pvalue.list)</sub></strong>. What is the probability distribution shown from this histogram? Does this surprise you?</li>

 <li>Plot a histogram illustrating the empirical sampling distribution of the t-statistic, i.e., <strong><sub>hist(sim$statistic.list,probabilit </sub>=</strong><strong><sub>TRUE)</sub></strong>. What is the probability distribution shown from this histogram?</li>

 <li>Run the following four lines of code:</li>

</ul>

<strong>t.test.sim(R=1000,mu1=10,mu2=10,sigma1=5,sigma2=5)$rejection.rate</strong>

<strong>t.test.sim(R=1000,mu1=10,mu2=12,sigma1=5,sigma2=5)$rejection.rate</strong>

<strong>t.test.sim(R=1000,mu1=10,mu2=14,sigma1=5,sigma2=5)$rejection.rate</strong>

<strong>t.test.sim(R=1000,mu1=10,mu2=16,sigma1=5,sigma2=5)$rejection.rate </strong>Comment on the results.

<ul>

 <li>Run the following four lines of code:</li>

</ul>

<strong>t.test.sim(R=10000,mu1=10,mu2=12,sigma1=10,sigma2=10,m=10,n=10)$rejection.rate</strong>

<strong>t.test.sim(R=10000,mu1=10,mu2=12,sigma1=10,sigma2=10,m=30,n=30)$rejection.rate</strong>

<strong>t.test.sim(R=10000,mu1=10,mu2=12,sigma1=10,sigma2=10,m=50,n=50)$rejection.rate</strong>

<strong>t.test.sim(R=10000,mu1=10,mu2=12,sigma1=10,sigma2=10,m=100,n=100)$rejection.rate </strong>Comment on the results.

<ul>

 <li><strong><sub>Extra credit: </sub></strong>Modify the <strong><sub>test.sim() </sub></strong>function to investigate how the power and size behave in the presence of heavy tailed data, i.e., investigate how <strong><sub>robust </sub></strong>the t-test is in the presence of violations from normality.</li>

</ul>

<strong>Hint: </strong>The Cauchy distribution and the students’ t-distribution with low df are both heavy tailed.