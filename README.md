# gssoc-25-PorQua-mentor-review


# Project
This is just a rough framework of all I'll be doing within this project

# Project Overview  

My project aims to advance **PorQua’s portfolio optimization, machine learning, and deliverables**, enhancing its theoretical and practical foundations to create a robust framework for real-world investment strategies.  

## Portfolio Optimization Framework  
I will develop **LinearProgram and ConvexProgram** classes as solver wrappers, mirroring QuadraticProgram’s structure—solving:  
\[
\min c^T w \quad \text{and} \quad \min f(w) \quad \text{subject to} \quad A w = b, \quad G w \leq h
\]
via **qpsolvers** (e.g., **CVXPY, Gurobi**) to support linear and convex problems alongside quadratic ones, ensuring solver flexibility and a unified API for seamless problem definition and solution.  

## Portfolio Optimization Objectives  
I’ll define **extensible objective classes**:  
- **MaximumUtility** will optimize a logarithmic utility function:  
  \[
  U(w) = \ln (w^T r)
  \]
  to reflect investor risk preferences.  
- **MaximumRatio** will target the **Sharpe ratio**:  
  \[
  \frac{w^T r - r_f}{\sqrt{w^T \Sigma w}}
  \]
  and explore **Sortino or Omega ratios**.  
- **MinimumRisk** will minimize metrics like **variance** \( w^T \Sigma w \), **CVaR**:  
  \[
  \alpha^{-1} \int_{-\infty}^{VaR} x dF(x)
  \]
  or **tracking error** \( ||w^T r - b||^2 \).  
- **EqualRiskContribution** will balance **marginal risk contributions**:  
  \[
  w_i \frac{\partial \sigma}{\partial w_i}
  \]
  across assets, all formulated to integrate with the optimization classes.  

## Multi-Objective Optimization  
I’ll enable **objective combinations**, such as **maximizing utility while minimizing risk**, using weighted objectives:  
\[
\lambda U(w) - (1 - \lambda) w^T \Sigma w
\]
to explore **trade-offs within a convex or quadratic framework**, ensuring theoretical coherence across solvers.  

## Constraints Implementation  
I’ll enhance constraints with **risk contribution bounds**, enforcing:  
\[
w_i \frac{\partial \sigma}{\partial w_i} \leq \kappa
\]
to prevent risk concentration. This complements **QuadraticProgram’s turnover linearization**:  
\[
|w - w_{\text{init}}| \leq \tau
\]
and introduces a **liquidity constraint**:  
\[
w_i \leq \frac{V_i}{V_{\text{total}}} \cdot 0.05
\]
which will be analyzed for impact on feasible sets and solver performance.  

## Machine Learning - Time Series Prediction (LSTM)  
I’ll implement **LSTM networks** to forecast **stock returns** \( r_{t+1} \) from historical sequences, designing preprocessing pipelines to normalize inputs (e.g., **log-returns**) and training models across horizons (e.g., **1-day, 5-day**), with theoretical validation against statistical benchmarks.  

## Machine Learning - Learning to Rank (LTR)  
I’ll develop an **LTR model** (e.g., **RankNet or LambdaRank**) to **order stocks by expected returns**, optimizing a **pairwise ranking loss function**:  
\[
- \sum_{i > j} \ln(1 + e^{-(s_i - s_j)})
\]
ensuring alignment with portfolio objectives through **ranked weight assignments**.  

## Machine Learning - Feature Generation  
I’ll create a suite of **technical indicators**—e.g., **moving averages, RSI, volatility**:  
\[
\sigma_t = \frac{1}{n} \sum (r_t - \bar{r})^2
\]
to enrich ML inputs, grounded in financial theory to **capture market dynamics**.  

## Machine Learning - Feature Selection  
I’ll apply **Recursive Feature Elimination (RFE), Lasso**:  
\[
\min ||y - X w||_2^2 + \lambda ||w||_1
\]
and **Random Forest importance scores** to select **the most predictive features**, enhancing model efficiency and interpretability.  

## Deliverables  
I will deliver:  
✅ **A full-featured optimization engine** spanning **linear, convex, and quadratic** problems.  
✅ **ML models (LSTM, LTR) for return prediction and ranking**.  
✅ **A technical feature suite** for model training and portfolio construction.  
✅ **Detailed documentation with tutorials**, ensuring accessibility for quants and newcomers alike.  

## Theoretical Approach  
1. **Analyze QuadraticProgram’s QP structure** and refine turnover/liquidity constraints.  
2. **Extend to LinearProgram and ConvexProgram**, integrating ML predictions into optimization objectives.  
3. **Develop a backtesting system** to assess **real-world performance**, ensuring solver-agnostic compatibility and mathematical rigor throughout.  



# Personal Data  
**Name:** Arsh Tulshyan  
**Affiliation:** B.Tech in Computer Engineering, Vidyalankar Institute of Technology  
**Location:** Mumbai, India  

## Studies and Programming Courses I’ve Taken  
- **Analysis of Algorithms & Advanced Data Structures** – Deep dive into algorithm efficiency, trees, and graph algorithms.  
- **Data Structures & OOP (Java)** – Core data structures and object-oriented programming principles.  
- **Structured Programming (C) & Python** – Fundamentals of programming, problem-solving approaches.  
- **DBMS & Computer Networks** – SQL, database design, network protocols, and security concepts.  
- **Operating Systems & Theory of Computation** – Process management, automata, computational complexity.  
- **Discrete Mathematics & Probability/Statistics** – Graph theory, combinatorics, probability distributions, hypothesis testing.  
- **Linear Algebra & Complex Numbers** – Matrices, eigenvalues, and applications in computing.  
- **Microprocessors & Computer Graphics** – Understanding CPU architectures, rendering techniques.  
- **Digital Logic Circuits & Hardware Fundamentals** – Circuit design, Boolean algebra, and networking basics.  
- **Quantum Physics & Professional Skills** – General understanding of quantum mechanics and career-oriented skills.  

## Some Projects I’ve Worked On  
- **[Advent of Code 2024](https://github.com/ash01825/AdventofCode-2024)** – Solved high-difficulty algorithmic challenges, refining my C++ and Python problem-solving skills.  
- **AI Crop Disease Prediction** – Built a deep-learning model for detecting crop diseases through image processing, improving accuracy for real-world agricultural applications.  
- **International Quant Championship (IQC)** – Active WorldQuant Brain contributor, participating in IQC to apply quantitative modeling in finance.  

## My Best Skills in Programming & Scientific Computing  
- **Programming:** Strong in **C++, Python, and Java**, focusing on efficiency and optimized implementations.  
- **Algorithms & Data Structures:** Advanced problem-solving with **dynamic programming, graph algorithms, and divide-and-conquer techniques**.  
- **Scientific Computing:** Hands-on experience with **probability theory, linear algebra, and numerical methods** in practical applications.  
- **Machine Learning & AI:** Solid grasp of **supervised learning, reinforcement learning, and their applications in quantitative finance**.  
- **Quantitative Finance:** Experience with **algorithmic trading, statistical modeling, alpha development, and backtesting**.  
- **Software Development:** Built **Flask-based web apps, worked with SQLite/SQL databases, and handled backend development**.  
- **Performance Optimization:** Strong understanding of **low-latency, high-performance coding**, especially in C++.  

## My Programming Style  
I mostly **code in C++** because of how powerful and fast it is. Python is great too, but honestly, it sometimes feels like a cheat code. That said, it’s fun and extremely useful. My approach is to **think through the best solution first, then start coding**—efficiency matters to me.  

I enjoy both **working solo and in teams**—it really depends on the project. If it’s a team effort, I focus on **clear documentation and making things simple for everyone**. I like things to be well-structured and easy to follow. 

My best skills and what I am most inclined towards are - Competitive Programming and Machine Learning. 

## Availability During the Program  
No conflicts—I’m fully committed to this project throughout the summer and will be working on it every day.  

## My Plans After GSoC  
I definitely see myself **continuing to contribute to PorQua** even after GSoC ends. My goal is to get into quant, and **GeomScale is the only GSoC org that aligns so well with math and finance**. Since PorQua is mentored by experts in quant, I’d be grateful for the chance to stay involved.  

## Am I More of a Theorist or a Hacker?  
I’d say I have a **hacker mindset**—I love experimenting and optimizing implementations. But with GeomScale, I’m drawn to the **deep mathematical and financial statistics side** because it fits perfectly with my goal of working in quant.  

##Hoping to here back soon 💫























