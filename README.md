# Investise
Don't be a fool. Consider your risks and rewards and invest wisely!
## Inspiration

The investment would make sense if we expected it to bring back more money than it costs. But returns are only one side of the story because it is dangerous - there can be a variety of outcomes. How does one compare different investments that can bring the same results on average, but show different levels of risk?

## What it does

**William Sharpe is our man.**

He introduced the _reward-to-variability ratio_ in 1966 that soon came to be called the **Sharpe Ratio**. 

It compares the expected return on two investment opportunities and calculates the additional return for each risk unit an investor can receive by choosing one over the other. In particular, it looks at the difference in the return on the two investments and compares the difference between the average deviation (as a risk level) of that difference. Sharpe's high rating means that the reward will be higher than the given risk amount. It is common to compare a certain period of time with a measure that represents the entire investment category.

The Sharpe rate is generally calculated for the portfolio and uses the risk-free interest rate as a measure. We will simplify our model and use stocks instead of portfolios. We will also use the stock index as a benchmark rather than a risk-free interest rate because both are readily available on daily frequencies and do not need to be involved in changing interest rates from annual to daily. Just remember that we will do the same calculation of portfolio returns and your risk-free rate of choice, e.g, the 3-month Treasury Bill Rate.

So let’s visualize and see for ourselves about Sharpe’s rating by counting down the shares of two tech giants Facebook and Amazon. As a benchmark, we will use the S&P 500 which measures the performance of 500 major US stocks. When we use the stock index instead of a risk level, the result is called Information Ratio and is used to mark a return on active portfolio management because it tells you how much to reimburse a given unit risk to your fund manager in terms of just putting your money in a low-cost fund.

## How we built it
**About the data**
This is the Stock Data:

<img width="1144" alt="Screenshot 2021-10-09 at 20 05 15" src="https://user-images.githubusercontent.com/92206277/136662391-94c16c06-5149-4cdb-a7ac-05c3fe96ce69.png">

This is the benchmarks data: 

![image](https://user-images.githubusercontent.com/92206277/136662418-8e01e478-12fe-46a5-8e51-02f94d4242fb.png)

Visualising the Amazon and Facebook Stock with insights about the features:

![image](https://user-images.githubusercontent.com/92206277/136662490-e1120038-6c56-4b9c-b820-b19295b5652c.png)

Visualising the S&amp;P 500 movements with insights about the features:

![image](https://user-images.githubusercontent.com/92206277/136662503-5b1e32c9-ce1a-4887-b72d-169acd0d5d6b.png)

Visualising the daily percentage change on Amazon and Facebook stock:

![image](https://user-images.githubusercontent.com/92206277/136662535-c9ab7271-15e3-4c8a-9153-32fdb560a3a8.png)

Visualising the daily percentage change on S&amp;P 500 stocks:

![image](https://user-images.githubusercontent.com/92206277/136662623-10f5f379-0b88-4f6d-b3d7-3beb8dabaee5.png)

Calculating the excess returns, basically the relative performance between Amazon or Facebook compared to the S&ampP 500 benchmark:

![image](https://user-images.githubusercontent.com/92206277/136662651-2aabb124-8f67-4c56-b679-6f1e02886d4c.png)

Step1 of calculating the Sharpe Ratio: Calcualting the Mean/ Average of Excess returns. Bar Plot has taken to see how each stock stands:

![image](https://user-images.githubusercontent.com/92206277/136662707-b39609ff-60d5-4b3c-a20a-3984136a0842.png)

Calculating the standard deviation, basically shows us the amount of risk an investment in the stocks implies as compared to an investment in the S&P 500.

![image](https://user-images.githubusercontent.com/92206277/136662763-7570e90e-b92d-40ac-a10a-efda3d53ae19.png)

Calculating the annualized sharpe ratio: 

![image](https://user-images.githubusercontent.com/92206277/136662828-ce440fef-8478-4b46-bdad-8808db64ad1d.png)

The Sharpe Ratio uses the difference in returns between the two investment opportunities under consideration.

However, our data show the historical value of each investment, not the _return_.

- [x] To calculate the return, we need to calculate the percentage change in value from one day to the next. We'll also take a look at the summary statistics because these will become our inputs as we calculate the Sharpe Ratio.

- [x] For the S&P 500 data, calculating daily returns works just the same way.

- [x] We need to calculate the relative performance of stocks compared to the S&P 500 benchmark. **This is calculated as the difference in returns between stock_returns and sp_returns for each day.**

**Now we can finally start computing the Sharpe Ratio.** 

- [x] First, we need to calculate the average of the excess_returns. This tells us how much more or less the investment yields per day as compared to the benchmark.

- [x] Next, we calculate the standard deviation of the excess_returns. This shows us the amount of risk investment in the stocks implies as compared to an investment in the S&P 500.

- [x] Now we just need to compute the ratio of avg_excess_returns and sd_excess_returns. 

- [x] The result is now finally the Sharpe ratio and indicates how much more (or less) return the investment opportunity under consideration yields per unit of risk.

- [x] The Sharpe Ratio is often annualized by multiplying it by the square root of the number of periods. We have used daily data as input, so we'll use the square root of the number of trading days (5 days, 52 weeks, minus a few holidays): √252

**Conclusion**

Given the two ratios of Sharpe, what investment should we go to? In 2016, Amazon had twice the Sharpe ratio than Facebook. This means that investing in Amazon has doubled compared to the S&P 500 for each risk unit an investor would have imagined. In other words, in terms of risk-adjusted terms, investing in Amazon would have been more attractive.

This difference was largely driven by differences in returns rather than risks between Amazon and Facebook. The risk of choosing Amazon over FB (as measured by standard deviations) was only slightly higher so that Amazon’s higher Sharpe rate kept it high due to Amazon’s high average daily return.
When faced with other investment options that offer a variety of returns and risks, the Sharpe Ratio assists in decision-making by adjusting the return on the risk difference and allows the investor to compare investment opportunities on equal terms, i.e., apples-on-apples basis.

## Challenges we ran into

The Sharpe Ratio uses the difference in returns between the two investment opportunities considered.
However, our data reflect the historical value of each investment, not the return.
To calculate the return, we need to calculate the percentage change in value from one day to the next. We will also look at the summary statistics as this will be our input as we calculate the Sharpe Ratio.

## Accomplishments that we're proud of

This being the first project I have in the field of data and analytics, everything that I did with the project was an achievement.

## What we learned

Playing around with data, sharpe ratio for finances, and sticking around with the idea even when you think it might not work out

## What's next for Investise

Hmm, well I intend to build this with a website with cool data feeding and visualizing type features. Basically generalizing it. Right now, this is just a prototype.
