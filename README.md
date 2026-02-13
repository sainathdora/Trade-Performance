<h1>Steps to run this</h1>
<ul>
  <li>Download the 2 .csv files(fear_greed_index, historical_data)</li>
  <li>Install Anaconda</li>
  <li>launch jupyter notebook</li>
  <li>Run all cells</li>
</ul>
<h2>Alternative: Use Google Colab</h2>
<ul>
  <li>Launch google colab</li>
  <li>Upload the the two .csv files into the notebook environment</li>
  <li>Run the desired cells</li>
</ul>

<h2>Methodology</h2>
<p>
  The analysis was conducted using a Regime-Specific Behavioral Audit. Instead of looking at profit in a vacuum, 
  we cross-referenced performance metrics against the Crypto Fear & Greed Index to determine how market sentiment alters 
  trader psychology and execution.
</p>
<ul>
  <li>
    <b>Data Preparation</b>: 211,000+ trades were classified into Fear or Greed regimes based on the daily index.
    <ul>Segmentation Logic: Accounts were categorized using a multi-factor matrix:
      <li><b>Activity Density</b>: Trade count relative to time.</li>
      <li><b>Risk Profile</b>: Standard Deviation ($STD$) of PnL and the Max Single Hit (Drawdown Proxy).</li>
      <li>Efficiency: Win Rate vs. Average PnL.</li>
      </ul>
  </li>
  <li><b>Risk-Reward Modeling</b>: Calculated the "Pain Ratio"—the number of average wins required to recover from a single maximum loss in each regime.</li>
</ul>
<hr>

<h2>II. Key Insights</h2>

<div>
<h4>1. The "Aggression Shift" Evidence</h4>
<p>Data shows a clear behavioral pivot when sentiment turns Greedy. While the Average PnL rises by 20.8%, the Max Single Hit increases by 230%.</p>
<p><strong>Finding:</strong> Traders are "sizing up" during Greed phases. The higher standard deviation (976 vs 871) confirms that positions are larger or more leveraged, leading to "Black Swan" events that are absent during Fearful regimes.</p>
</div>

<div>
<h4>2. Fear as the key Engine</h4>
<p>Contrary to popular belief, Fear is the group's most profitable regime in absolute terms ($5.38M vs $4.86M).</p>
<p><strong>Finding:</strong> The group relies on high-frequency "Mean Reversion." A 33% higher trade volume in Fear suggests that traders are more active during market panics, capitalizing on an 83.79% win rate provided by volatility spikes.</p>
</div>

<div>
<h4>3. The Fragility of Greed</h4>
<p>The "Pain Ratio" in Greed is significantly worse. In Fear, it takes approximately 800 trades to recover a max loss; in Greed, it takes approximately 2,190 trades.</p>
<p><strong>Finding:</strong> The "quality" of Greed profits is lower because the risk of a single "blow-up" trade is exponentially higher. This indicates a systemic breakdown in stop-loss discipline during periods of bullish exuberance.</p>
</div>

<hr>

<h2>III. Strategic Recommendations</h2>

<div>
<h4>Recommendation 1: Tactical De-leveraging in Greed</h4>
<p><strong>Target:</strong> The "Aggressive Gambler" segment.</p>
<p><strong>Action:</strong> Implement a Hard Leverage Cap (e.g., 5x max) specifically when the Fear & Greed Index exceeds 75.</p>
<p><strong>Rationale:</strong> Since average profit only increases marginally in Greed while outlier risk triples, the Expected Value of high-leverage trades is negative. Capping size protects cumulative profit from being erased by a single catastrophic error.</p>
</div>

<div>
<h4>Recommendation 2: Liquidity Priority for Scalpers in Fear</h4>
<p><strong>Target:</strong> The "High-Freq Scalper" segment.</p>
<p><strong>Action:</strong> Allocate additional API rate limits and capital to these accounts when the Index drops below 30.</p>
<p><strong>Rationale:</strong> These traders demonstrate a high-probability edge (84% win rate) during panics. Increasing their frequency during these windows maximizes absolute PnL while the statistical risk remains lower than in Greed regimes.</p>
</div>

<hr>
