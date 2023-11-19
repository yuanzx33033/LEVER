# LEVER: Online Adaptive Sequence Learning Framework for High-Frequency Trading

This is a table of techinical indicators used in LEVER architecture as described in the paper.

<p align="center">
  <img width="950" height="380.5" src=./technical_indicator_table.png>
</p>


## Settings of Technical Indicators ##
\noindent\textbf{Security trend}. The $N$-period exponential moving average function ($ema(N)$) smooths out price data by creating a constantly updated average price. Here, we adopt a slow line $ema(N_1)$ and a fast line $ema(N_2)$ to create a `tunnel', and observe whether a check line $ema(N_3)$ trespasses the tunnel, where $N_1 > N_3 > N_2 > 0$. According to the ``Vegas Tunnel Method''~\cite{li2019modular}, security price is probably in a price uptrend if check line crosses the tunnel from bottom to top and downtrend otherwise. 
We introduce five different features to quantify such trend pattern, i.e., $\textbf{x}^{tr}_{t} = \{x^{1, tr}_{t}, x^{2, tr}_{t}, x^{3, tr}_{t}, x^{4, tr}_{t}, x^{5, tr}_{t}\}\in \mathbb{R}^{5 \times 1}$. 
% Given a specific time granularity (e.g. 1-min level), discrete trading transactions are repeatedly processed, and directly influence the ultimate OHLC of time-windowed quotes. Moving average

\noindent\textbf{Security volatility}. The $N$-period bollinger bands \cite{murphy1999technical} are comprised of upper band, middle band, and lower band, plotted at a standard deviation level above and below a moving average of the price. They serve as dynamic SRLs to identify the market periods of low and high volatility. 
% marked by contraction in the bands, and periods of high volatility, marked by expansion of the bands. 
Likewise, we develop five distinct features to study such volatility pattern, represented as $\textbf{x}^{bb}_{t} = \{x^{1, bb}_{t}, x^{2, bb}_{t}, x^{3, bb}_{t}, x^{4, bb}_{t}, x^{5, bb}_{t}\}\in \mathbb{R}^{5 \times 1}$. 

\noindent\textbf{Trading volume}. The transaction intensity reveals the dominating power of buy or sell, which can be reflected from order queue in terms of five unique features, denoted as $\textbf{x}^{oq}_{t} = \{x^{1, oq}_{t}, x^{2, oq}_{t},$ $x^{3, oq}_{t},
x^{4, oq}_{t}, x^{5, oq}_{t}\}\in \mathbb{R}^{5 \times 1}$.

Due to the page limit, we have detailed the above technical indicators via an external link\footnote{\blue{https://github.com/yuanzx33033/LEVER}}.
