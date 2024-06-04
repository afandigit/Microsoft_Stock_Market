<h1> Microsoft_Stock_Market </h1>
<h2> Using Python and Time Series Applications to analyze and predict stock market trends </h2>

<img align="right"  width="400" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/23d0bcb7-718c-47b9-b111-c82d38e86aab" alt="stock market" /> 
<img align="left"  width="400" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/c9649078-26cf-4066-a6bd-801e81eb03ed" alt="stock market" /> 

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

<h2>Goal :</h2>
The study aims to develop a model using machine learning methods to <b>analyze stock trading risks</b> and <b>make informed decisions</b> on <b>whether to stay in the market or exit</b>, essentially determining whether to buy or sell stocks.


<h2>Dataset :</h2>

<p>I have used data from Yahoo MSFT stock (Microsoft Corporation) from 1986/03/14 to 2022/12/20.</p>	

<table> <thead> <tr> <th>Date</th> <th>Open</th> <th>High</th> <th>Low</th> <th>Close</th> <th>Adj Close</th> <th>Volume</th> </tr> </thead> <tbody> <tr> <td>1986-03-14</td> <td>0.097222</td> <td>0.102431</td> <td>0.097222</td> <td>0.100694</td> <td>0.062980</td> <td>308160000</td> </tr> <tr> <td>1986-03-17</td> <td>0.100694</td> <td>0.103299</td> <td>0.100694</td> <td>0.102431</td> <td>0.064067</td> <td>133171200</td> </tr> <tr> <td>1986-03-18</td> <td>0.102431</td> <td>0.103299</td> <td>0.098958</td> <td>0.099826</td> <td>0.062437</td> <td>67766400</td> </tr> <tr> <td>1986-03-19</td> <td>0.099826</td> <td>0.100694</td> <td>0.097222</td> <td>0.098090</td> <td>0.061351</td> <td>47894400</td> </tr> <tr> <td>1986-03-20</td> <td>0.098090</td> <td>0.098090</td> <td>0.094618</td> <td>0.095486</td> <td>0.059723</td> <td>58435200</td> </tr> 
    <tr> <td> .... </td> <td> .... </td> <td> .... </td> <td> .... </td> <td> .... </td> <td> .... </td> <td> .... </td> </tr>
    <tr> <td>2022-12-13</td> <td>261.690002</td> <td>263.920013</td> <td>253.070007</td> <td>256.920013</td> <td>256.920013</td> <td>42196900</td> </tr> <tr> <td>2022-12-14</td> <td>257.130005</td> <td>262.589996</td> <td>254.309998</td> <td>257.220001</td> <td>257.220001</td> <td>35410900</td> </tr> <tr> <td>2022-12-15</td> <td>253.720001</td> <td>254.199997</td> <td>247.339996</td> <td>249.009995</td> <td>249.009995</td> <td>35560400</td> </tr> <tr> <td>2022-12-16</td> <td>248.550003</td> <td>249.839996</td> <td>243.509995</td> <td>244.690002</td> <td>244.690002</td> <td>86088100</td> </tr> <tr> <td>2022-12-19</td> <td>244.860001</td> <td>245.210007</td> <td>238.710007</td> <td>240.449997</td> <td>240.449997</td> <td>29668800</td> </tr> </tbody> </table>

<p>This dataset contains a date column that is organized and consecutive, we can consider this dataset as a time series dataset.</p>

<img align="center"  width="800" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/53227b34-10ed-467d-a5b4-53a972da2225" alt="dataset" />


<h4>Open/Close price over time of this dataset</h4>
<img align="center"  width="800" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/990abb61-90ff-4ea6-b2ec-3f6864e0fa07" alt="Open/Close price over time of this dataset" />

<h4>After zooming in on a specific time range</h4>

<img align="center"  width="1000" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/c8ef6270-999a-45dc-b603-3c46f091973e" alt="dataset" />

<img align="center"  width="800" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/d8a6e2ac-6879-420e-b599-87734bbdf2db" alt="Last 100 records" />

<h4>Candlestick charts for the same the last range time</h4>

<img align="center"  width="800" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/b17c69d0-818a-4ca3-a602-6f1b885cb9e6" alt="Last 100 records - Candlestick charts" />


<h2>Stock Price Information</h2>

    <div class="section">
      <h3>1. The <strong>Open</strong> Price</h3>
      <p>
        The <strong>Open</strong> price represents <em>the price</em> at which
        <strong>a stock was first traded</strong> during the current trading
        session.
      </p>
    </div>

    <div class="section">
      <h3>2. The <strong>Close</strong> Price</h3>
      <p>
        The <strong>Close</strong> price represents <em>the price</em> at which
        <strong>a stock was last traded</strong> during the current trading
        session.
      </p>
    </div>

    <div class="section">
      <h3>3. The <strong>High</strong> Price</h3>
      <p>
        The <strong>High</strong> price represents <em>the highest price</em> at
        which <strong>a stock was traded</strong> during the current trading
        session.
      </p>
    </div>

    <div class="section">
      <h3>4. The <strong>Low</strong> Price</h3>
      <p>
        The <strong>Low</strong> price represents <em>the lowest price</em> at
        which <strong>a stock was traded</strong> during the current trading
        session.
      </p>
    </div>

    <div class="section">
      <p>
        The Open and Close prices give an idea of the general market trend for
        the stock in question.
      </p>
      <ul>
        <li>
          1- If the <strong>Close price is higher than the Open price</strong>,
          it is likely that the stock experienced a price increase during the
          trading session, indicating a bullish trend.
        </li>
        <li>
          2- If the <strong>Close price is lower than the Open price</strong>,
          it is likely that the stock experienced a price decrease during the
          trading session, indicating a bearish trend.
        </li>
        <li>
          3- The <strong>High</strong> and <strong>Low</strong> prices give an
          idea of
          <strong>the market volatility for the stock in question</strong>.
          <ul>
            <li>
              - If the <em>spread</em> between the High and Low prices
              <strong>is large</strong>, it indicates that the stock experienced
              <strong>high volatility</strong> during the trading session.
            </li>
            <li>
              - If the <em>spread</em> is <strong>small</strong>, it indicates
              that the stock experienced <strong>low volatility</strong>.
            </li>
          </ul>
        </li>
      </ul>
    </div>


<h4>Bullish Trand Vs. Bearish Trand</h4>
<img align="left"  width="450" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/ed5bfe04-4cb3-44ee-8b4a-b83051f4fee5" alt="Bullish" /> 

<img align="right"  width="450" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/c9649078-26cf-4066-a6bd-801e81eb03ed" alt="Bearish" /> 



<h4></h4>

<h4></h4>


<h4></h4>


<h2>Realization :</h2>

Our analysis is (monthly-based & Daily-based), and all the decisions are made the first trading day of the month. For a reason which will be clarified by the following code, our analysis will start from 24 months after January 1986 and end the month before November 2022.

Then I selected the columns to use for the candlestick chart ("Open", "High", "Low", "Close")

<h4>I converted this unsupervised problem to a supervised problem</h4>

So if we return to our dataset and represent it with the candlestick chart, we will see variations over time in Mirosoft's actions.
Our objective is to <b>predict whether we will leave or stay in the market at the start of each trading period</b>.

In the image bellow, I create another column <i>'Target'</i> that specify <b>if the action in the current trading session was increased or decreased ?</b>. so i calculate the difference between the close price and open price then if it's positive it was a <b>Bullish trend = 1</b> or <b>Bearish trend = 0</b>.


<img align="center"  width="600" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/14047347-9865-4747-8504-d7a35fad27ee" alt="data labeling" /> 

This target is made by the current period but we want to predict for the next period, will it be bullish or bearish?

<img align="center"  width="600" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/e203f5a0-4597-40b4-ba66-36d957030d81" alt="data labeling" /> 

So for this we had to shift all these values ​​up so that each period will have a new target value which says that the next trading period will be bullish or bearish.

<b>Next Step i train Machine learning and deep learning models to predict for new data if we gonna stay on the market or not.</b>

<b>Using Random Forest ... </b>

<img align="center"  width="500" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/582e661d-5b07-460f-a546-14bea199161f" alt="rf" /> 


<b>Using Random Forest + GridSearchCV... </b>

<img align="center"  width="500" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/89da954d-1ce4-42d4-b0c0-3bd9477542c3" alt="rf-gridsearchcv" /> 

we notice that the results were improved ...


<b>Using Random Forest + GridSearchCV + Feature extraction</b>

I Calculated the logarithmic difference between consecutive prices ... 

<img align="center"  width="500" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/2a97fd1c-1d15-45b5-aea2-79518c0f827d" alt="rf-gridsearchcv-fe" /> 

<p>
I used <b><i>logarithmic differencing</i></b> to normalize data, a common technique in financial analysis to visualize price variations in percentage terms using relative values. </br></br></br>Logarithmic differencing is useful for data with increasing trends over time, such as stock price data. </br>It involves taking the natural logarithm of each price value, then calculating the difference between consecutive values to compute relative growth rates between periods. This method helps visualize stock price growth trends for better understanding of price changes, even with significant long-term increases. It enables easy comparison of growth trends between different stocks or periods.
</p>

<img align="center"  width="500" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/de35b3c6-dd4b-4c50-b9e8-28d2ac4970d3" alt="logarithm-diff" />

then i have normilized data ...

<img align="center"  width="500" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/b0d5188f-8418-4124-a6dd-c60e600161d8" alt="logarithm-diff" />

<img align="center"  width="500" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/dd1d2a7d-7c59-4a6e-889b-75b791f3548f" alt="logarithm-diff" />

<b>Then i deploy the model to TELL US ... WHETHER STAY OR EXIT THE MARKET :) </b>

<img align="center"  width="600" src="https://github.com/afandigit/Microsoft_Stock_Market/assets/106676180/9fe54d25-0beb-482c-9130-3d46277f928f" alt="deploy" />








