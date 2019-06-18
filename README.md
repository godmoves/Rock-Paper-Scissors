## Regret Matching for Rock-Paper-Scissors

Regret Matching algorithm for computing Rock-Paper-Scissors Nash Equilibrium

### Algorithm

**Regret Matching algorithm** <a href="https://www.codecogs.com/eqnedit.php?latex=\hat{H}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\hat{H}" title="\hat{H}" /></a> will maintain the **vector of weights assigned to experts** <a href="https://www.codecogs.com/eqnedit.php?latex=p" target="_blank"><img src="https://latex.codecogs.com/svg.latex?p" title="p" /></a>. After loss vector is revealed we can compute cumulative regret with respect to an expert <a href="https://www.codecogs.com/eqnedit.php?latex=i" target="_blank"><img src="https://latex.codecogs.com/svg.latex?i" title="i" /></a> at time <a href="https://www.codecogs.com/eqnedit.php?latex=t" target="_blank"><img src="https://latex.codecogs.com/svg.latex?t" title="t" /></a> (it expresses how we regret not listening particular expert <a href="https://www.codecogs.com/eqnedit.php?latex=i" target="_blank"><img src="https://latex.codecogs.com/svg.latex?i" title="i" /></a>):

<div align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=R_{i,&space;t}=L^{t}_{\hat{H}}-L^{t}_{i}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?R_{i,&space;t}=L^{t}_{\hat{H}}-L^{t}_{i}" title="R_{i, t}=L^{t}_{\hat{H}}-L^{t}_{i}" /></a>
</div>

Having that, experts’ weights are updated with the formula:

<div align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=w_{i,t}&space;=&space;(R_{i,t})_&plus;&space;=&space;\max(0,&space;R_{i,t})" target="_blank"><img src="https://latex.codecogs.com/svg.latex?w_{i,t}&space;=&space;(R_{i,t})_&plus;&space;=&space;\max(0,&space;R_{i,t})" title="w_{i,t} = (R_{i,t})_+ = \max(0, R_{i,t})" /></a>
</div>

and finally components of our vector <a href="https://www.codecogs.com/eqnedit.php?latex=p^t" target="_blank"><img src="https://latex.codecogs.com/svg.latex?p^t" title="p^t" /></a> (a probability distribution vector over <a href="https://www.codecogs.com/eqnedit.php?latex=N" target="_blank"><img src="https://latex.codecogs.com/svg.latex?N" title="N" /></a> experts) are given by:

<div align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=p_i^t&space;=&space;\begin{cases}&space;w_{i,t}/\sum_{j&space;\in&space;N}{w_{j,t}}&space;&&space;{\rm&space;if}&space;\sum_{j&space;\in&space;N}{w_{j,t}}&space;>&space;0&space;\\&space;1/N&space;&&space;{\rm&space;otherwise}&space;\end{cases}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?p_i^t&space;=&space;\begin{cases}&space;w_{i,t}/\sum_{j&space;\in&space;N}{w_{j,t}}&space;&&space;{\rm&space;if}&space;\sum_{j&space;\in&space;N}{w_{j,t}}&space;>&space;0&space;\\&space;1/N&space;&&space;{\rm&space;otherwise}&space;\end{cases}" title="p_i^t = \begin{cases} w_{i,t}/\sum_{j \in N}{w_{j,t}} & {\rm if} \sum_{j \in N}{w_{j,t}} > 0 \\ 1/N & {\rm otherwise} \end{cases}" /></a>
</div>

You can find a more comprehensive explanation of this algorithm [here](https://int8.io/counterfactual-regret-minimization-for-poker-ai/).

### Uasge

Check `regret_matching.ipynb` for more infomation.

### Result

Both players find the Nash equilibrium of the game and play rock/paper/scissors with roughly the same probability.

<div align="center">
<table>
<tr>
<td><img src="a.png" /></td>
<td><img src="b.png" /></td>
</tr>
<tr>
<th>strategy of player a</th>
<th>strategy of player b</th>
</tr>
</table>
</div>
