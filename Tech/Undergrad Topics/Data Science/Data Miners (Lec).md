### Data Mining - Lecture 1
- Mine massive data sets** *(databases, transaction records and log files)* 
- **Uncover hidden patterns, trends, correlations, and anomalies in data sets** *to improve business decision-making and strategic planning*

> **Objectives**
> - Review of Data Science / Data Analytics
> - Understand the importance of Data Preprocessing
> - Apply different data pre-processing techniques

---

## Core Concepts

### Data vs Information

| Term            | Definition                                                                                                                                |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **Data**        | Facts and statistics collected for reference or analysis; things known or assumed as facts, forming the basis of reasoning or calculation |
| **Information** | What is conveyed by a particular arrangement or sequence of things; data as processed, stored, or transmitted                             |

---

### Types of Data

| Type | Description |
|------|-------------|
| **Qualitative (Numerical)** | Represents numbers where arithmetic operations make sense |
| ↳ *Discrete* | Countable, exact values with finite possibilities (e.g., number of students) |
| ↳ *Continuous* | Infinite possible values, not always exact (e.g., height, temperature) |
| **Quantitative (Categorical)** | Values that represent names or labels — words, objects, pictures, observations, symbols |

---

### The Six Vs of Big Data

> (Visual content in slides — commonly: **Volume, Velocity, Variety, Veracity, Value, Variability**)

---

## Taxonomy of Data Analytics

```
Descriptive  →  What happened?
Diagnostic   →  Why did it happen?
Predictive   →  What will happen?
Prescriptive →  What should we do?
Cognitive    →  How do we replicate human thought?
```

| Type | Description |
|------|-------------|
| **Descriptive** | Summarizes/condenses data to extract patterns; produces reports and dashboards |
| **Predictive** | Extracts models from data for future predictions |
| **Diagnostic** | Diagnoses problems exhibited through data |
| **Prescriptive** | Combines insights from the first three to support decisions; recommends optimal solutions |
| **Cognitive** | Unfolds hidden patterns and replicates human thought |

---

### Predictive Analytics Algorithms

**Supervised Learning**
- Classification
- Regression
- Time Series Analysis

**Unsupervised Learning**
- Clustering
- Association Analysis
- Sequential Pattern Analysis
- Text Mining / Social Media Sentiment Analysis

---

## Data Mining

> Also known as **Knowledge Discovery in Data (KDD)** — the process of uncovering patterns and valuable information from large datasets (big data).

**Two main purposes:**
1. **Describe** the target dataset
2. **Predict** outcomes using machine learning algorithms

---

##  Levels of Measurement

| Scale        | Description                                                     | Example             |
| ------------ | --------------------------------------------------------------- | ------------------- |
| **Nominal**  | Categorized only; no order                                      | Hair color, gender  |
| **Ordinal**  | Can be ordered/ranked                                           | 1st, 2nd, 3rd place |
| **Interval** | Measured on a scale; zero is just another point                 | Time of day         |
| **Ratio**    | Zero is a fixed origin; allows comparisons like "twice as much" | Weight              |

---

## Types of Datasets

| Type | Description |
|------|-------------|
| **Record** | Collection of records with a fixed set of attributes |
| **Graph** | Depicts interactions between multiple entities |
| **Ordered Data** | Spatial, temporal, sequential, or genetic sequence |
| **Time Series** | A single attribute tracked over time |

---

## Data Quality

**Why preprocess data?** A multidimensional view of data quality:

| Dimension | Description |
|-----------|-------------|
| **Accuracy** | Correct or wrong, accurate or not |
| **Completeness** | Not recorded, unavailable |
| **Consistency** | Some modified but some not; dangling references |
| **Timeliness** | Timely updates? |
| **Believability** | How trustworthy is the data? |
| **Interpretability** | How easily can the data be understood? |

---

## Major Tasks in Data Preprocessing

### 1. Data Cleaning
- Fill in missing values
- Smooth noisy data
- Identify or remove outliers
- Resolve inconsistencies

### 2. Data Integration
Combines data from multiple sources into a coherent store.

**Key challenges:**
- **Schema integration** (e.g., `A.cust-id` ↔ `B.cust-#`)
- **Entity identification problem** (e.g., "Bill Clinton" = "William Clinton")
- **Data value conflicts** (different representations or scales)

**Handling Redundancy:**
- Object identification (same attribute, different names)
- Derivable data (one attribute derived from another)
- Detected via **correlation analysis** and **covariance analysis**

#### Correlation Analysis (Nominal) — Chi-Square Test (χ²)
- Larger χ² → more likely the variables are related
-  Correlation ≠ causality

**Example:**

| | Play Chess | Not Play Chess | Sum |
|--|--|--|--|
| Like Sci-Fi | 250 (90) | 200 (360) | 450 |
| Not Like Sci-Fi | 50 (210) | 1000 (840) | 1050 |
| **Sum** | 300 | 1200 | 1500 |

> Numbers in parentheses are expected counts.

#### Correlation Analysis (Numeric) — Pearson's Coefficient

$$r_{A,B} = \frac{\sum(a_i b_i) - n\bar{A}\bar{B}}{n\sigma_A\sigma_B}$$

| Value | Meaning |
|-------|---------|
| `r > 0` | Positively correlated |
| `r = 0` | Independent |
| `r < 0` | Negatively correlated |

#### Covariance (Numeric Data)

$$Cov(A,B) = \frac{\sum(a_i b_i)}{n} - \bar{A}\bar{B}$$

| Value | Meaning |
|-------|---------|
| `Cov > 0` | A and B tend to be larger than expected together |
| `Cov < 0` | If A is large, B tends to be small |
| `Cov = 0` | Independent (but not always true conversely) |

**Example:** Stocks A and B with values (2,5), (3,8), (5,10), (4,11), (6,14):
- E(A) = 4, E(B) = 9.6
- Cov(A, B) = 4 → **Rise together** 

---

### 3. Data Reduction

> Obtain a reduced representation of the dataset that produces the same (or nearly the same) analytical results.

#### 3a. Dimensionality Reduction

**Curse of Dimensionality:**
- As dimensions increase → data becomes increasingly sparse
- Distance/density measures lose meaning
- Subspace combinations grow exponentially

**Techniques:**
- **Wavelet Transforms**
- **Principal Component Analysis (PCA)**
- **Supervised / nonlinear techniques** (feature selection)

##### PCA Steps
1. Normalize input data (each attribute in the same range)
2. Compute k orthonormal vectors (principal components)
3. Sort components by decreasing significance (variance)
4. Eliminate weak components (low variance)
5. Works for **numeric data only**

##### Attribute Subset Selection
- **Redundant attributes**: Duplicate info from other attributes
- **Irrelevant attributes**: No useful information for the task at hand

**Heuristic Methods:**
- Best single attribute (significance test)
- Step-wise feature selection (add best one at a time)
- Step-wise attribute elimination (remove worst one at a time)
- Optimal branch and bound

##### Attribute Creation (Feature Generation)
- Attribute extraction (domain-specific)
- Attribute construction (combining features)
- Data discretization

---

#### 3b. Numerosity Reduction

**Parametric Methods** (assume a model):
- Store only model parameters, discard raw data
- Linear regression, Multiple regression, Log-linear models

**Non-Parametric Methods:**
- Histograms (equal-width or equal-depth partitioning)
- Clustering (store centroids)
- Sampling

##### Regression Analysis

| Type | Formula |
|------|---------|
| **Linear** | Y = wX + b |
| **Multiple** | Y = b₀ + b₁X₁ + b₂X₂ |
| **Log-linear** | Approximates discrete multidimensional probability distributions |

##### Sampling Methods

| Type | Description |
|------|-------------|
| **Simple Random (SRSWR)** | Equal probability; selected object is returned |
| **Simple Random (SRSWOR)** | Equal probability; selected object is removed |
| **Stratified** | Population divided into homogenous groups; samples drawn proportionally |
| **Cluster** | Population divided into clusters; clusters randomly selected |

##### Data Cube Aggregation
- Lowest level = base cuboid (individual entities)
- Multiple levels of aggregation reduce data size further
- Use the smallest representation sufficient for the task

---

#### 3c. Data Compression
- **String compression**: Lossless, limited manipulation without expansion
- **Audio/video**: Lossy, progressive refinement
- Dimensionality and numerosity reduction are also forms of compression

---

### 4. Data Transformation & Discretization

**Methods:**
- **Smoothing**: Remove noise
- **Attribute/feature construction**: Create new attributes from existing ones
- **Aggregation**: Summarization, data cube construction
- **Normalization**: Scale values to a specified range
- **Discretization**: Concept hierarchy climbing

#### Normalization Methods

| Method | Formula | Notes |
|--------|---------|-------|
| **Min-Max** | `v' = (v - min_A) / (max_A - min_A) × (new_max - new_min) + new_min` | Maps to [new_min, new_max] |
| **Z-Score** | `v' = (v - μ) / σ` | Uses mean and std dev |
| **Decimal Scaling** | `v' = v / 10^j` | j = smallest int where max(|v'|) < 1 |

**Min-Max Example:** Income $73,600 in range [$12,000, $98,000] → mapped to [0.0, 1.0]:
$$v' = \frac{73600 - 12000}{98000 - 12000} = 0.716$$

**Z-Score Example:** μ = 54,000, σ = 16,000:
$$v' = \frac{73600 - 54000}{16000} = 1.225$$

#### Discretization

**Three attribute types:**
- **Nominal**: Unordered set (e.g., color)
- **Ordinal**: Ordered set (e.g., academic rank)
- **Numeric**: Real numbers

**Methods:**
- **Binning**: Equal-width or equal-depth
- **Histogram analysis**: Top-down split
- **Clustering**: Unsupervised
- **Decision-tree analysis**: Supervised
- **Chi-square analysis**: Unsupervised, bottom-up merge

##### Simple Discretization: Binning

| Type | Description |
|------|-------------|
| **Equal-width** | Range divided into N intervals of equal size; outliers may dominate |
| **Equal-depth** | Each interval contains ~same number of samples; good for skewed data |

#### Concept Hierarchy Generation

- Organizes attribute values hierarchically
- Facilitates **drill-down** and **roll-up** in data warehouses
- Can be defined by domain experts or auto-generated

**Nominal Data Example:**
```
street < city < state < country
{Urbana, Champaign, Chicago} < Illinois
```

**Auto-generation logic:** Attribute with the **most distinct values** → lowest hierarchy level.

---
# Feature Selection & Regression - Lecture 2

---

## Feature Selection

> Aims to extract only the most "informative" features and remove noisy, irrelevant, and redundant features. It is a common way to minimize the problem of excessive and irrelevant features.

**Three main approaches (Lab Activity):**
- **Univariate Selection** — reduces the number of input variables when developing a predictive model
- **Feature Importance** — assigns a score to input features based on how useful they are at predicting a target variable
- **Correlation** — statistical summary of the relationship between variables

---

## Principal Component Analysis (PCA) — Recap

> Reduces the number of dimensions in large datasets by transforming potentially correlated variables into a smaller set of **principal components**.

**Why use PCA?**
- Extracts the most informative features while preserving relevant information
- Reduces model complexity
- Combats the **curse of dimensionality**

### PCA Steps (Review)

1. Normalize input data — each attribute falls within the same range
2. Compute k orthonormal (unit) vectors (principal components)
3. Each input data vector is a linear combination of k principal component vectors
4. Sort principal components by decreasing significance/strength
5. Reduce size by eliminating weak components (low variance)
6. Works for **numeric data only**

---

## Linear Regression

### Simple Linear Regression

> A machine learning technique to predict values from **one** independent variable.

**Equation:**
```
y = b0 + b1 * x1
```
- `y` = target/dependent variable
- `x1` = independent variable
- `b0` = y-intercept (value of y when x1 = 0)
- `b1` = slope (change in y per unit change in x1)

---

### Multiple Linear Regression

> Extension of Simple Linear Regression where the model depends on **more than one** independent variable.

**Equation:**
```
y = b0 + b1*x1 + b2*x2 + ... + bn*xn
```

**Assumptions:**

| Assumption | Description |
|------------|-------------|
| **Linearity** | Linear relationship between dependent and independent variables |
| **Multivariate Normality** | Residuals are normally distributed |
| **No Multicollinearity** | Independent variables are not highly correlated with each other |
| **Homoscedasticity** | Variance of residuals is consistent across all levels of independent variables |
| **Sample Size** | At least two independent variables required |

**Common Problems:**
- **Overfitting** — adding more independent variables doesn't always improve predictions
- **Multicollinearity** — independent variables correlated with each other, not just with the dependent variable

**To avoid multicollinearity and overfitting:** use correlations, scatter plots, and simple regression checks.

---

## Logistic Regression

> Models the **probability** of an event occurring depending on the values of independent variables. Used to classify observations or predict binary outcomes.

**Used to:**
- Model probability of an event occurring
- Predict the effect of variables on a binary response variable
- Classify observations by estimating probability of belonging to a category

### Types of Logistic Regression

| Type | Target Variable | Example |
|------|----------------|---------|
| **Binary** | Two possible outcomes | Cancer or No Cancer |
| **Multinomial** | Three or more nominal (unordered) categories | Type of wine |
| **Ordinal** | Three or more ordered categories | Restaurant rating (1–5 stars) |

---

### Key Statistical Concepts

#### Degrees of Freedom (DF)
> The number of independent pieces of information used to calculate an estimate. Usually calculated as: **n – 1** (for a single sample).

**Example:** A set of 3 numbers that must add to a fixed mean has **DF = 2** — once two numbers are chosen, the third is fixed.

#### P-Value
> Measures the probability of obtaining observed results assuming the null hypothesis (H0) is true.

| Threshold | Significance |
|-----------|-------------|
| P < 0.05 | Statistically significant |
| P < 0.001 | Statistically highly significant |

- **H0 (Null hypothesis):** No relationship between variables
- **H1 (Alternative hypothesis):** A relationship exists
- Lower p-value → greater statistical significance → reject H0

#### Confidence Interval
> A range of values likely to contain the true value of a population parameter with a specified degree of confidence.

#### R-Squared (R²)
> Coefficient of determination — how much percentage variation in the dependent variable is explained by the independent variable.

| R² Value | Interpretation |
|----------|---------------|
| 0 | Model explains 0% of the relationship |
| 0.5 | Model explains 50% of the relationship |
| 1 | Model explains 100% of the relationship |

---

### Probability, Odds, and Odds Ratio

| Concept | Definition |
|---------|-----------|
| **Probability** | Fraction of times you expect an event to occur; ranges from 0 to 1 |
| **Odds** | Probability the event occurs ÷ probability the event does not occur |
| **Odds Ratio** | How odds change with a 1-unit increase in a variable (holding others constant) |

---

### Bernoulli Distribution in Logistic Regression

> The dependent variable follows the **Bernoulli distribution** with unknown probability p.
- Success = 1, Failure = 0
- Probability of success = p, failure = q = 1 – p
- Logistic regression estimates unknown p for any given linear combination of independent variables

---

### Logistic Regression Example — Credit Score

**Model Data:** creditScore (predictor), approved (0 or 1, binary)

**Sample calculation** (creditScore = 720):
- Estimated probability of approval ≈ **76.68%**

**Reverse calculation:**
- For 75% chance (odds 3:1) → creditScore ≈ **714**
- For 80% chance (odds 4:1) → creditScore ≈ **733**

---
# Clustering - Lecture 3

---

## What is Cluster Analysis?

> **Cluster:** A collection of data objects that are similar within the same group and dissimilar to objects in other groups.

**Key characteristics:**
- **Unsupervised learning** — no predefined classes; learning by observation
- Also called: data segmentation, clustering

**Typical applications:**
- Stand-alone tool to get insight into data distribution
- Preprocessing step for other algorithms

---

## Applications of Cluster Analysis

- **Data Reduction** — summarization, compression (e.g., image processing via vector quantization)
- **Hypothesis Generation & Testing** — prediction based on groups
- **Finding K-Nearest Neighbors** — localizing search to one or a few clusters
- **Outlier Detection** — outliers are "far away" from any cluster

**Real-world domains:**
- Biology: taxonomy (kingdom → phylum → class → order → family → genus → species)
- Information retrieval: document clustering
- Marketing: customer segmentation for targeted programs
- City planning: house grouping by type, value, location
- Earthquake studies: clustering epicenters along fault lines
- Climate: atmospheric and ocean pattern discovery

---

## What is Good Clustering?

| Property | Description |
|----------|-------------|
| **High intra-class similarity** | Objects within the same cluster are cohesive |
| **Low inter-class similarity** | Clusters are distinctive from each other |

**Depends on:** the similarity measure used, implementation quality, and ability to discover hidden patterns.

---

## Basic Steps to Develop a Clustering Task

1. **Feature selection** — select relevant info; minimize redundancy
2. **Proximity measure** — define similarity of two feature vectors
3. **Clustering criterion** — cost function or rules
4. **Clustering algorithm** — choose appropriate method
5. **Validation** — clustering tendency test
6. **Interpretation** — integrate with applications

---

## Major Clustering Approaches

### Partitioning Approach
> Constructs various partitions evaluated by a criterion (e.g., minimizing sum of squared errors).

**Typical methods:** k-means, k-medoids (PAM), CLARANS

### Hierarchical Approach
> Creates a hierarchical decomposition using some criterion.

**Typical methods:** Diana, Agnes, BIRCH, CAMELEON

### Density-Based Approach
> Based on connectivity and density functions.

**Typical methods:** DBSCAN, OPTICS, DenClue

### Grid-Based Approach
> Based on a multiple-level granularity structure.

**Typical methods:** STING, WaveCluster, CLIQUE

### Other Approaches
- **Model-based:** EM, SOM, COBWEB
- **Frequent pattern-based:** p-Cluster
- **User-guided / constraint-based:** COD, constrained clustering
- **Link-based:** SimRank, LinkClus

---

## Partitioning Methods

### K-Means Algorithm

**Steps:**
1. Partition objects into k nonempty subsets
2. Compute centroids (mean point) of current clusters
3. Assign each object to the cluster with the nearest centroid
4. Repeat steps 2–3 until no assignment changes

**Determining k:**

| Method | Description |
|--------|-------------|
| **Empirical** | k ≈ √(n/2) for n data points |
| **Elbow Method** | Find the "turning point" in sum of within-cluster variance vs. k |
| **Cross Validation** | Divide data into m parts; test each; compare quality across different k values |

**Complexity:** O(tkn) — t = iterations, k = clusters, n = objects

**Strengths vs. Weaknesses:**

| Strengths | Weaknesses |
|-----------|-----------|
| Efficient: O(tkn) | Needs k specified in advance |
| Works well for continuous n-dimensional data | Sensitive to noisy data and outliers |
| | Not suitable for non-convex cluster shapes |
| | Only for objects in continuous space |

**Variations:**
- **k-modes** — for categorical data (uses modes instead of means)
- **k-prototype** — mixture of categorical and numerical data

---

### K-Medoids / PAM (Partition Around Medoids)

> Instead of the mean, uses the **most centrally located object** in a cluster as the reference point. More robust against outliers.

**PAM Algorithm:**
1. Arbitrarily choose k objects as initial medoids
2. Assign each remaining object to nearest medoid
3. Randomly select a non-medoid object (O_random)
4. Compute total cost of swapping
5. Swap if quality improves
6. Repeat until no change

**Complexity:** O(k(n–k)²)

---

## Hierarchical Clustering

> Creates a hierarchy of clusters. Does not require pre-specifying k. Visualized using a **dendrogram**.

### AGNES — Agglomerative Nesting (Bottom-Up)
- Each observation starts as its own cluster (leaf)
- At each step, the two most similar clusters are merged
- Continues until all points form one cluster

### DIANA — Divisive Analysis (Top-Down)
- All observations start in one cluster (root)
- At each step, the most heterogeneous cluster is split
- Continues until each observation is its own cluster

---

### Distance Between Clusters

| Method | Formula | Description |
|--------|---------|-------------|
| **Single Link** | min(tip, tjq) | Smallest distance between any two elements |
| **Complete Link** | max(tip, tjq) | Largest distance between any two elements |
| **Average** | avg(tip, tjq) | Average distance between elements |
| **Centroid** | dist(Ci, Cj) | Distance between cluster centroids |
| **Medoid** | dist(Mi, Mj) | Distance between cluster medoids |

---

### AGNES – Single Link Example

**Data:** 18, 22, 25, 27, 42, 43

Step-by-step merging (merge closest pair each step):
1. Merge 42 & 43 (distance = 1)
2. Merge 25 & 27 (distance = 2)
3. Merge 22 into {25, 27} (distance = 3)
4. Merge 18 into {22, 25, 27} (distance = 4)
5. Merge all into one cluster

**Final tree:** `((42, 43), (((25, 27), 22), 18))`

---

### AGNES – Complete Link

> At each step, merge the two clusters whose **maximum** pairwise distance is the smallest.

**Example (A, B, C, D):**
- Merge A & B (shortest distance)
- New distance C to {A,B} = max(C→A, C→B) = 40
- New distance D to {A,B} = max(D→A, D→B) = 100
- Continue until all merged

---

### Cluster Geometry Measures

| Measure | Description |
|---------|-------------|
| **Centroid** | The "middle" (mean) of a cluster |
| **Radius** | √(average distance from any point to centroid) |
| **Diameter** | √(average mean squared distance between all pairs of points) |

---

## Density-Based Methods

### DBSCAN

**Key parameters:**
- **Eps (ε):** Maximum radius of the neighbourhood
- **MinPts:** Minimum number of points in an ε-neighbourhood

**Concepts:**

| Concept | Definition |
|---------|-----------|
| **Core point** | A point p where |N_Eps(p)| ≥ MinPts |
| **Directly density-reachable** | p is within Eps of a core point q |
| **Density-reachable** | p is reachable from q through a chain of directly density-reachable points |
| **Density-connected** | Both p and q are density-reachable from a common core point o |
| **Cluster** | A maximal set of density-connected points |
| **Noise/Outlier** | A point not reachable from any core point |

**Advantages:** Discovers clusters of arbitrary shape; handles noise.
**Weakness:** Sensitive to parameter settings (Eps and MinPts).

---

### OPTICS (1999)
> Ordering Points To Identify the Clustering Structure — produces a special ordering of the database with reference to its density-based clustering structure. Good for both automatic and interactive cluster analysis.

---

## Grid-Based Methods

### STING (Statistical Information Grid)
- Divides spatial area into rectangular cells at multiple resolution levels
- Statistical info of each cell (count, mean, σ, min, max, distribution type) stored beforehand
- Top-down approach to answer spatial queries
- **Advantages:** Query-independent, easy to parallelize, incremental update — O(K)
- **Disadvantage:** Cluster boundaries are only horizontal or vertical (no diagonal)

### CLIQUE
- Automatically identifies subspaces of high-dimensional data that allow better clustering
- Both density-based and grid-based
- A unit is **dense** if the fraction of data points in it exceeds the input threshold
- **Steps:** Partition space → identify subspaces with clusters (Apriori principle) → identify clusters → generate minimal descriptions

---

## Evaluating Clustering Quality

| Type | Description |
|------|-------------|
| **External (supervised)** | Compare clustering against ground truth using external criteria |
| **Internal (unsupervised)** | Evaluate compactness and separation of clusters (e.g., Silhouette coefficient) |
| **Relative** | Directly compare different clustering results (e.g., different k values) |

**Common External Measures:**
- Matching-based: Purity, F-measure
- Entropy-based: NMI (Normalized Mutual Information)
- Pair-wise: Jaccard coefficient, Rand statistic, Fowlkes-Mallows measure

---
# Similarity & Dissimilarity Measures - Lecture 4

---

## Core Concepts

> **Similarity:** A numerical measure of the degree to which two objects are alike. Higher when objects are more alike.

> **Dissimilarity:** A numerical measure of how different two objects are. Lower when objects are more alike. Minimum is often 0.

Both are also called **proximity**. The term **distance** is often used as a synonym for dissimilarity.

**Range:** Both measures are non-negative. Similarity ranges from 0 (highly dissimilar) to some finite/infinite value (highly similar).

---

## Proximity by Data Type

### Nominal (Single Attribute)

> Measures are binary — 1 if the two objects have the **same** attribute value, 0 otherwise.

**Example (Gender = {Male, Female}):**

| Object | Gender |
|--------|--------|
| Ram | Male |
| Sita | Female |
| Laxman | Male |

Similarity(Ram, Laxman) = 1; Similarity(Ram, Sita) = 0

---

### Nominal (Multiple Attributes)

**Dissimilarity formula:**

$$d(i,j) = \frac{p - m}{p}$$

where `p` = total number of attributes, `m` = number of attributes with matching values.

**Example — 1 attribute (Color):**

| ID | Color |
|----|-------|
| 1 | Red |
| 2 | Green |
| 3 | Blue |
| 4 | Green |

Dissimilarity matrix:

|  | 1 | 2 | 3 | 4 |
|--|---|---|---|---|
| 1 | 0 | | | |
| 2 | 1 | 0 | | |
| 3 | 1 | 1 | 0 | |
| 4 | 1 | 0 | 1 | 0 |

---

### Binary Attributes

#### Symmetric Binary
> No preference for which outcome is coded 0 or 1 (e.g., Gender: M/F). Both values are equally important.

**Simple Matching Coefficient:**
$$sim(i,j) = \frac{f_{11} + f_{00}}{f_{01} + f_{10} + f_{11} + f_{00}}$$

#### Asymmetric Binary (Jaccard Coefficient)
> One outcome (1) is more important than the other (0). The value 0 is considered less significant.

**Four quantities computed:**
- `a` (f₁₁) = attributes equal to 1 for **both** objects i and j
- `b` (f₀₁) = attributes equal to 0 for i but 1 for j
- `c` (f₁₀) = attributes equal to 1 for i but 0 for j
- `d` (f₀₀) = attributes equal to 0 for **both** objects

**Jaccard Similarity:**
$$J(i,j) = \frac{a}{a + b + c}$$

*(The d term — both zero — is ignored as it's considered less meaningful)*

**Jaccard Dissimilarity:**
$$d(i,j) = 1 - J(i,j) = \frac{b + c}{a + b + c}$$

**Example — Customers C1, C2, C3 with item attributes:**

| | item1 | item2 | item3 | item4 | item5 | item6 | item7 | item8 | item9 |
|--|--|--|--|--|--|--|--|--|--|
| C1 | 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 1 |
| C2 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 |
| C3 | 1 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |

---

### Categorical (Nominal) Attribute

**Similarity:**
$$sim(i,j) = \frac{m}{p}$$

where `m` = number of matching attribute values, `p` = total number of attributes.

**Dissimilarity:**
$$d(i,j) = 1 - sim(i,j) = \frac{p - m}{p}$$

---

### Interval-Scaled (Numeric) Data — Distance Metrics

**Minkowski Distance (generalization):**
$$d(i,j) = \left(\sum_{k=1}^{n} |x_{ik} - x_{jk}|^r\right)^{1/r}$$

| r value | Distance type | Characteristics |
|---------|--------------|-----------------|
| **r = 1** | **Manhattan (City Block)** | Sum of absolute differences; less sensitive to outliers |
| **r = 2** | **Euclidean** | Straight-line distance; sensitive to outliers |
| **r → ∞** | **Chebyshev** | Maximum of absolute differences |

**Manhattan Distance:**
$$d(i,j) = \sum_{k=1}^{n} |x_{ik} - x_{jk}|}$$

**Euclidean Distance:**
$$d(i,j) = \sqrt{\sum_{k=1}^{n} (x_{ik} - x_{jk})^2}$$

---

### Ordinal Attributes

> Values come from an ordered set (e.g., {S, M, L} or {Ex, A, B, C}).

**Normalization formula:**
$$z_{if} = \frac{r_{if} - 1}{M_f - 1}$$

where `r_if` is the rank of object i for attribute f, and `M_f` is the number of possible states.

**Example — Size = {S, M, L}:**

| Size | Rank | Normalized |
|------|------|-----------|
| S | 1 | 0.0 |
| M | 2 | 0.5 |
| L | 3 | 1.0 |

**Example — Quality = {Ex, A, B, C} (Ex > A > B > C):**

| Quality | Rank | Normalized |
|---------|------|-----------|
| C | 1 | 0.0 |
| B | 2 | 0.333 |
| A | 3 | 0.666 |
| Ex | 4 | 1.0 |

After normalization, treat ordinal attributes as interval-scaled.

---

### Mixed Attributes

When a dataset has a mix of nominal, ordinal, and numeric attributes, combine dissimilarity measures:

$$d(i,j) = \frac{\sum_{f=1}^{p} \delta_{ij}^{(f)} d_{ij}^{(f)}}{\sum_{f=1}^{p} \delta_{ij}^{(f)}}$$

where `δ = 0` if the attribute is missing or asymmetric binary with both = 0; otherwise `δ = 1`.

**Example — Objects with Nominal, Ordinal, Numeric attributes:**

| Object | A (Nominal) | B (Ordinal) | C (Numeric) |
|--------|------------|------------|------------|
| 1 | Code A | Excellent | 45 |
| 2 | Code B | Fair | 22 |
| 3 | Code C | Good | 64 |
| 4 | Code A | Excellent | 28 |

Separate dissimilarity matrices are computed for each attribute type, then combined using the formula above.

**Final dissimilarity matrix (combined):**

|  | 1 | 2 | 3 | 4 |
|--|---|---|---|---|
| 1 | 0 | | | |
| 2 | 0.85 | 0 | | |
| 3 | 0.65 | 0.83 | 0 | |
| 4 | 0.13 | 0.71 | 0.79 | 0 |

---

## Non-Metric Similarity — Cosine Similarity

> Used for complex objects with many symbolic entities (e.g., text documents with keywords).

**Formula:**
$$cos(x, y) = \frac{x \cdot y}{||x|| \cdot ||y||}$$

**Interpretation:**

| Angle | Cosine Value | Meaning |
|-------|-------------|---------|
| 0° | 1 | Same orientation — identical |
| 90° | 0 | Perpendicular — no similarity |
| 180° | -1 | Opposite — completely dissimilar |

**Range:** –1 to +1. Smaller angles → larger cosine values → greater similarity.

**Common use:** Information retrieval, text mining.

---

## Choosing the Right Measure

### Similarity Measure Selection

| Factor | Consideration |
|--------|--------------|
| **Data type** | Continuous → Pearson correlation; Categorical → Jaccard; Text → Cosine |
| **Scale sensitivity** | Some measures are sensitive to scale differences between features |
| **Task** | Cosine for text/IR; Jaccard for clustering/recommendation systems |

### Dissimilarity Measure Selection

| Factor | Consideration |
|--------|--------------|
| **Data type** | Hamming for binary/string; Euclidean for continuous numeric |
| **Scale of data** | If feature ranges differ greatly, consider normalizing or use Manhattan |
| **Dimensionality** | For high-dimensional data, Mahalanobis distance may be more robust |

---
# Text Analytics - Lecture 5

---

## What is Text Analysis?

> The automated process of translating large volumes of **unstructured text** into quantitative data to uncover insights, trends, and patterns.

**Deals with unstructured data** — conversations, declarations, tweets, comments — that doesn't fit neatly into the row-and-column structure of relational databases, yet represents the vast majority of data available in the real world.

---

## Text Formats

| Format | Description | Example |
|--------|-------------|---------|
| **Structured** | Organized into rows/columns | Database table with Name, Bank, Loan Amount |
| **Free Text** | Natural language prose | "Mr. John Cruz purchased Toyota Sedan..." |
| **Multimedia** | HTML, hyperlinks, embedded media | `<a href>John Cruz</a> purchased <a href>a car</a>` |

---

## Difficulties in NLP

**Language is tricky — common challenges:**

| Challenge | Description | Example |
|-----------|-------------|---------|
| **Word-level ambiguity** | Same word has different parts of speech or meanings | "design" can be a noun or verb; "root" has multiple meanings |
| **Syntactic ambiguity** | Sentence structure is unclear | "A man saw a boy with a telescope." |
| **Anaphora resolution** | Unclear pronoun reference | "John persuaded Bill to buy a TV for himself." (himself = John or Bill?) |
| **Presupposition** | Implied background knowledge | "He has quit smoking." implies he smoked before |

---

## NLP Pipeline

### Data Pre-processing Steps

```
Raw Text
   ↓ Convert Accented Characters
   ↓ Expand Contractions
   ↓ Tokenization
   ↓ Stop Words Removal
   ↓ Stemming / Lemmatization
   ↓ Parts of Speech Tagging
   ↓ Ready for Modelling
```

### Modelling Techniques

- Bag of Words, TF-IDF, Word Embeddings
- Sentiment Analysis
- Keywords Extraction
- Named Entity Recognition (NER)
- Topic Modelling
- Summarization

---

## Pre-processing Techniques

### 1. Convert Accented Characters
Normalize special characters: `Latté → latte`, `Café → cafe`

### 2. Expand Contractions
`don't → do not`, `can't → can not`

### 3. Tokenization
> Splits a phrase, sentence, or document into smaller units (tokens = words).

**Purpose:** Interpret meaning by analyzing individual words; count words in text.

**Example:** `"I saw a cat"` → tokens: `"I"`, `"saw"`, `"a"`, `"cat"`

---

### 4. Stemming
> Reduces a word to its **root/stem** by removing prefixes and suffixes.

**Common stemmers:** Porter stemmer, Krovetz stemmer

| Word | Suffix Removed | Stem |
|------|---------------|------|
| cats | s | cat |
| caring | ing | care / car |
| plants | s | plant |

**Benefits:**
- Reduces input dimensions
- Makes training data more dense
- Reduces dictionary size
- Normalizes words across a document

---

### 5. Lemmatization
> Performs **morphological analysis** of words to find their base (lemma).

**Common tools:** WordNet Lemmatizer (NLTK), spaCy, TextBlob, Stanford CoreNLP

| Word | Morphological Info | Lemma |
|------|--------------------|-------|
| Helps | 3rd person singular, present tense | help |
| Helping | Noun/adjective | helping |

> **Stemming vs Lemmatization:** Stemming is faster but cruder (may produce non-real words). Lemmatization is more accurate and always produces a real word.

---

### 6. Parts of Speech (POS) Tagging
> Assigns a part of speech (noun, verb, adjective, etc.) to each word in a sentence. Performed at the token level.

---

### 7. Stop Words Removal
> Common words that add little meaning are filtered out before processing.

**Examples:** the, is, in, for, to, a, an, etc.

> Stop words act as bridges to ensure grammatical correctness but carry little informational value.

---

## Text Representation — Term Weights

### Bag of Words (BoW)

> Represents text as a vector of word frequencies from a predefined vocabulary. Ignores grammar and word order.

**Components:**
- **Vocabulary** — list of all unique words in a corpus
- **Feature vector** — n-dimensional vector of numerical features

**Example (vocabulary of 5 words: good, job, miss, not, all):**

| | good | job | miss | not | all |
|--|--|--|--|--|--|
| Sentence 1: "...good job...not miss..." | 1 | 1 | 1 | 1 | 0 |
| Sentence 2: "...not good at all" | 1 | 0 | 0 | 1 | 1 |

---

### N-Gram

> An N-token sequence of words.

| N-gram | Name | Example |
|--------|------|---------|
| 2 words | Bigram | "really good", "not good", "your homework" |
| 3 words | Trigram | "not at all", "turn off light" |

**Bigrams from "This is not good at all":**
`"This is"`, `"is not"`, `"not good"`, `"good at"`, `"at all"`

---

### Term Frequency Approaches

| Approach | Description |
|----------|-------------|
| **Binary term occurrence** | 1 if the term occurs in a document, 0 otherwise |
| **Term Frequency (TF)** | Number of occurrences of a term in a document |
| **TF-IDF** | Combines term frequency with inverse document frequency |

#### TF-IDF Formula

$$TF(i,j) = \frac{n(i,j)}{\sum n(i,j)}$$

$$IDF = 1 + \log\left(\frac{N}{dN}\right)$$

$$TF\text{-}IDF = TF \times IDF$$

where:
- `n(i,j)` = number of times term i occurs in document j
- `N` = total number of documents
- `dN` = number of documents containing the term

> **Intuition:** TF-IDF gives high weight to terms that appear frequently in a specific document but rarely across the corpus — making them more discriminating and meaningful.

**Count Vectorizer vs TF-IDF:**
- Count Vectorizer gives raw frequency with respect to vocabulary index
- TF-IDF considers the overall weight of words across all documents

---

## Text Classification

> The process of categorizing text into predefined groups.

### Three Approaches

#### 1. Rule-Based (Lexicon-Based)
> Texts are grouped based on handcrafted linguistic rules. Users define a list of words for each category.

**Examples:**
- `Robredo, Lacson, Marcos` → politics
- `Christianity, Islam, Atheism` → religion

#### 2. Machine-Based
> Classification is learned from pre-labeled datasets using Bag of Words features.

#### 3. Hybrid Approach
> Combination of rule-based and machine-based. Uses word lists to label the dataset; classification is iteratively improved by updating the word list.

---

## Machine Learning Algorithms for Text Classification

### Naïve Bayes

> Based on **Bayes' theorem** — describes the relationship of conditional probabilities.

**Probability formula for document d in class c:**

$$P(c|d) \propto P(c) \prod_{k=1}^{n_d} P(t_k | c)$$

where P(c) is the prior probability of class c, and P(t_k|c) is the conditional probability of term t_k in class c.

**Example — Naïve Bayes classification:**

| | Class h (yes) | Class -h (no) |
|--|--|--|
| Words in class | 19 | 9 |
| P(Love\|class) | 5/19 | 2/9 |
| P(Pain\|class) | 1/19 | 4/9 |
| P(Joy\|class) | 5/19 | 1/9 |
| P(Kick\|class) | 1/19 | 2/9 |

**For Document 7 = "Love Pain Joy Love Kick":**
- P(h|d7) ∝ (2/3) × (5/19) × (1/19) × (5/19) × (5/19) × (1/19) ≈ 0.000067
- P(-h|d7) ∝ (1/3) × (2/9) × (4/9) × (1/9) × (2/9) × (2/9) ≈ 0.00018
- **Result: Class = NO (–h)** since P(-h|d7) > P(h|d7)

---

### Support Vector Machine (SVM)

> A supervised learning algorithm for classification. Creates the best decision boundary (hyperplane) to segregate n-dimensional space into classes.

**Key concepts:**

| Term | Definition |
|------|-----------|
| **Hyperplane** | The decision boundary separating classes |
| **Support Vectors** | Data points closest to the hyperplane |
| **Margin** | Distance between support vectors and the hyperplane |

**Types:**
- **Linear SVM** — for linearly separable data (2 classes)
- **Non-linear SVM** — for non-linearly separable data (uses kernel trick; e.g., adding dimension z = x² + y²)

---

### Random Forest

> A supervised ensemble learning algorithm. Combines multiple decision trees to solve complex classification problems.

**Key principles:**
- Feature variables should have actual (not guessed) values
- Predictions from each tree must have **low correlations** with each other
- More trees → higher accuracy → less overfitting

**Advantages:**
- Less training time than many other algorithms
- High accuracy on large datasets
- Handles missing data well

---

## Sentiment Analysis

> Classification of texts according to the emotion they convey — typically **positive**, **negative**, or **neutral**.

**Applications:**
- Market analysis
- Social media monitoring
- Customer feedback analysis
- Market research

**Challenges (nuance):**
- "I like to travel, sometimes" — mixed sentiment
- "I do not dislike cabin cruise" — double negative
- "It looks like it's going to rain" — not sentiment despite surface-level negativity

---

## Lexicon-Based Approaches

> Words are labeled as positive, negative, or neutral using a **valence dictionary**.

**Example:**
- "Good people sometimes have bad days."
- `"Good"` → positive; `"bad"` → negative; other words → neutral

### Types of Lexicon-Based Approaches

#### Dictionary-Based
1. Start with a small set of seed words
2. Expand using online dictionaries/thesaurus/WordNet (synonyms & antonyms)
3. Expand until no new words can be added
4. Refine by manual inspection

#### Corpus-Based
- **Statistical approach** — words with higher frequency in positive texts → positive polarity; higher in negative → negative polarity; equal → neutral
- **Semantic approach** — assigns sentiment values based on synonyms/antonyms of words

**Popular Lexicon-Based Tools:**
- TextBlob
- VADER
- SentiWordNet

---
# Topic Modelling - Lecture 6

---

## What is Topic Modelling?

> An **unsupervised machine learning technique** that scans a set of documents, detects word and phrase patterns, and automatically clusters word groups and similar expressions that best characterize the documents.

**Core idea:** Recognizing words from topics present in a document or corpus by counting words and grouping similar word patterns to infer topics within unstructured data.

**Example topics detected from a corpus:**

| Topic 1 (Technology) | Topic 2 (Business) | Topic 3 (Entertainment) |
|----------------------|--------------------|------------------------|
| Computer | Sell | Play |
| Phone | Sale | Film |
| System | Product | Movie |
| Internet | Advertising | Theater |
| Machine | Market | Production |
| Website | Consumer | Star |
| Cloud | | Director / Stage |

---

## Use Cases

- **Structure of documents** — understanding relationships among topics
- **Topics through time** — how topics evolve across time periods
- **Characterizing events** — identifying what topics define specific events
- **Membership models** — e.g., grouping by ethnicity, demographics, or communities

---

## Topic Modelling Methods

### Two Main Approaches

| Method | Full Name | Key Feature |
|--------|-----------|-------------|
| **LSA** | Latent Semantics Analysis | Uses SVD on document-term matrix |
| **LDA** | Latent Dirichlet Allocation | Probabilistic; models topic mixtures per document |

**LDA Assumptions:**
- **Distributional hypothesis** — similar topics use similar words
- **Statistical mixture hypothesis** — documents talk about several topics

---

## Latent Semantics Analysis (LSA)

**Input:** Document-term matrix
- Rows = different documents
- Columns = different terms
- Values = word counts

**Processing:** Uses Bag-of-Words and/or TF-IDF

**Output:** Finds themes across various documents by reducing the matrix using Singular Value Decomposition (SVD).

---

## Latent Dirichlet Allocation (LDA)

> LDA is a **generative probabilistic model**. The name breaks down as:
> - **Latent** = hidden (topics are hidden variables)
> - **Dirichlet** = type of probability distribution used
> - **Allocation** = assignment of words to topics

### Core Principles

- Every document consists of a **mix of topics**
- Every topic consists of a **mix of words**
- Every document is a **probability distribution over topics**
- Every topic is a **probability distribution over words**

---

### How LDA Works

```
1. Choose the number of topics K you think exist in your corpus
         ↓
2. Randomly assign each word in each document to one of K topics
         ↓
3. For every word and its topic assignment in each document:
     → Look at: how often does the topic occur in the document?
     → Look at: how often does the word occur in the topic overall?
         ↓
4. Assign the word a new (better) topic based on step 3
         ↓
5. Repeat through multiple iterations until topics stabilize
         ↓
6. Interpret the resulting topics
```

### LDA Example

**Documents → Topic assignments:**

| Document | Topic Mix |
|----------|-----------|
| Doc 1 | Mostly Topic A |
| Doc 2 | Mostly Topic B |
| Doc 3 | Mix of A & B |

**Discovered topics:**
- Topic A → **Food** (words cluster around food-related terms)
- Topic B → **Animals** (words cluster around animal-related terms)

---

## LSA vs LDA

| Feature | LSA | LDA |
|---------|-----|-----|
| **Approach** | Algebraic (SVD) | Probabilistic (Bayesian) |
| **Interpretability** | Lower | Higher |
| **Topic representation** | Continuous values | Probability distributions |
| **Handles polysemy** | Partially | Better |
| **Computation** | Faster | Slower (iterative) |

---
#  Sentiment Analysis - Lecture 7

---

## What is Sentiment Analysis?

> **Contextual mining of text** that identifies and extracts subjective information from a source material. A common text classification tool that analyzes an incoming message and determines whether the underlying sentiment is **positive**, **negative**, or **neutral**.

---

## Three Approaches to Sentiment Analysis

### 1. Rule-Based

> Software is trained to classify keywords in text based on **lexicons** (vocabulary groups that describe the author's intent).

**How it works:**
- Positive lexicon: words like *"affordable," "fast," "well-made"*
- Negative lexicon: words like *"expensive," "slow," "poorly made"*
- Software scans text for words in each lexicon, tallies a total sentiment score based on volume and weight of words

**Pros:** Transparent, interpretable, no training data needed
**Cons:** Misses context, sarcasm, and complex language

---

### 2. Machine Learning (Automatic)

> An algorithm is trained to gauge sentiment using words in the text **and the order in which they appear**.

**Common classification algorithms:**

| Algorithm | Description |
|-----------|-------------|
| **Linear Regression** | Describes a value (Y) based on a set of features (X) |
| **Naïve Bayes** | Uses Bayes' theorem to categorize words in text |
| **Support Vector Machine (SVM)** | Fast, efficient; solves two-group classification problems |
| **Random Forest** | Ensemble learning; maintains high accuracy |
| **Deep Learning (DL)** | Neural networks; mimics human brain function; most powerful but resource-intensive |

---

### 3. Hybrid

> Combines both ML and rule-based capabilities to **optimize accuracy and speed**.

**Trade-off:** Highly accurate but requires more resources — time and technical capacity — than the other two approaches.

---

## Types of Sentiment Analysis

### 1. Fine-Grained (Graded) Sentiment Analysis

> Groups text into different emotions and measures the **level** of emotion expressed. Allows precise polarity classification beyond just positive/negative/neutral.

**Scale example:**
- Rating 1–4 → Negative sentiment
- Rating 5–10 → Positive sentiment

**Polarity spectrum:** Very Negative → Negative → Neutral → Positive → Very Positive

---

### 2. Aspect-Based Sentiment Analysis (ABSA)

> Analyzes sentiment toward **specific aspects** of a product, service, or idea rather than the overall text.

**Example:**
- Review: *"The webcam seems to go on and off randomly."*
- ABSA identifies: **Aspect** = webcam | **Sentiment** = negative
- This allows product teams to pinpoint exactly *what* customers are unhappy with.

---

### 3. Emotion Detection

> Determines specific emotions such as joy, sadness, fear, worry, frustration, indifference, restlessness, and shock.

**Key characteristics:**
- Uses **lexicons** (words/expressions for specific emotions) + ML classifiers
- Seeks to understand the **psychological state** of the author — their frame of mind and intentions
- More complex than fine-grained or ABSA
- Moves beyond simple polarity (positive/negative) to identify granular emotional states

---

## Comparison of Sentiment Analysis Types

| Type | Granularity | Output | Use Case |
|------|-------------|--------|----------|
| **Fine-Grained** | Polarity levels | Very positive to very negative | Product ratings, customer surveys |
| **Aspect-Based (ABSA)** | Feature-specific | Sentiment per product feature | Product reviews, support tickets |
| **Emotion Detection** | Specific emotions | Joy, fear, sadness, anger, etc. | Social media monitoring, mental health |

---

## Comparison of Approaches

| Approach | Accuracy | Speed | Resources | Interpretability |
|----------|----------|-------|-----------|-----------------|
| **Rule-Based** | Moderate | Fast | Low | High |
| **Machine Learning** | High | Moderate | Moderate | Moderate |
| **Hybrid** | Highest | Moderate | High | Moderate |

---

## Python Implementation

**Key libraries:**
- **Pandas** — data handling
- **NLTK** — natural language processing
- **SentimentIntensityAnalyzer** — sentiment analysis (from NLTK's VADER)

```python
import pandas as pd
import nltk
from nltk.sentiment import SentimentIntensityAnalyzer

sia = SentimentIntensityAnalyzer()
scores = sia.polarity_scores("This product is amazing!")
# Returns: {'neg': 0.0, 'neu': 0.323, 'pos': 0.677, 'compound': 0.5719}
```

**VADER compound score interpretation:**
- ≥ 0.05 → Positive
- ≤ -0.05 → Negative
- Between -0.05 and 0.05 → Neutral

---

## Relation to Previous Lectures

| Concept | Connection |
|---------|-----------|
| Lexicon-based approaches (Lec05) | Foundation for Rule-Based SA |
| Naïve Bayes (Lec05) | Used in ML-based SA |
| SVM (Lec05) | Used in ML-based SA |
| Random Forest (Lec05) | Used in ML-based SA |
| TF-IDF / BoW (Lec05) | Feature extraction for ML-based SA |

---
# Lecture 08 – Time Series Forecasting

---

## What is a Time Series?

> A **sequence of data points** that occur in successive order over some period of time.

**Time series forecasting** uses information about historical values and associated patterns to predict future activity — most often relating to **trend analysis**, **cyclical fluctuation analysis**, and **seasonality**.

Forecasting is built on three principles: **autoregression (p)**, **differencing (d)**, and **moving averages (q)**.

**Real-world examples:** Weather data, temperature, stock prices, quarterly sales, population change.

---

## Time Series Usage

| Application | Description |
|-------------|-------------|
| **Clustering** | Group time series that exhibit similar patterns |
| **Classification** | Identify time series belonging to a specific category |
| **Searching** | Find similar time series within large datasets (e.g., correlated stocks, similar customer behaviors) |
| **Forecasting** | Make future predictions |
| **Trend & Seasonality** | Understand long-term and periodic patterns |
| **Visualization** | Interpret complex patterns and support data-driven decisions |

---

## Challenges in Time Series Analysis

### Similarity is Context-Dependent
- **Human Bias** — metrics for similarity are chosen based on intuition, which can introduce bias
- **Inconsistent Interpretations** — different analysts may define similarity differently
- **Parameter Sensitivity** — different parameter choices lead to different results
- **Domain-Specific Definitions** — specialized fields use domain-specific metrics not universally understood

### Technical Challenges
- **Sampling Rate Differences** — one series collected every minute vs. another every hour creates comparison difficulties
- **Noise** — distorts the underlying signal, leading to:
  - Distorted trend and seasonality detection
  - Imprecise forecasting models (model fits noise rather than signal)
  - False anomalies (hard to distinguish from random fluctuations)
- **Missing Values** — impact quality of analysis and predictions

---

## How to Analyze a Time Series

```
1. Collect and clean the data (preprocessing)
         ↓
2. Prepare visualizations (time vs. key feature)
         ↓
3. Model/estimate trend and seasonality → remove them → get a stationary series
         ↓
4. Apply statistical forecasting techniques
         ↓
5. Convert forecasted values back to original scale (apply trend & seasonality constraints)
```

---

## Components of a Time Series

### 1. Trend
> The **long-term pattern** of a time series — the variable can increase or decrease over time.

| Trend Type | Description |
|------------|-------------|
| **Upward** | Values generally increasing over time |
| **Downward** | Values generally decreasing over time |
| **Stationary/Horizontal** | No clear increasing or decreasing pattern; mean is constant |

---

### 2. Cyclical
> Any pattern showing **up and down movement around a given trend**. The duration depends on the type of business/industry and is usually **at least 2 years**.

> Unlike seasonality, the duration and timing of cycles are not fixed and often unknown beforehand.

---

### 3. Seasonality
> **Periodic behavior** — regular fluctuations that occur during the same month(s) every year or the same quarter every year.

**Example:** Retail sales peak every December.

**Two forms of seasonality:**

| Model | Formula | Description |
|-------|---------|-------------|
| **Additive** | Y(t) = T(t) + S(t) + C(t) + I(t) | Seasonal variation amplitude is **independent** of the level |
| **Multiplicative** | Y(t) = T(t) × S(t) × C(t) × I(t) | Seasonal variation amplitude is **connected** to the level |

Where: O = original, T = trend, S = seasonal, C = cyclical, I = irregular

> **When to use which:** If seasonal swings stay the same size as the series grows → additive. If they grow proportionally with the series → multiplicative.

---

### 4. Irregular / Residuals / Noise
> The **unpredictable, random component** of a time series. Represents dynamic changes in an organization or market that cannot be captured or modeled.

**Goal of modeling:** Capture all components (T, S, C) so that the only remaining unexplained part is this random component.

---

## Stationarity

> **A stationary time series** is one whose statistical properties (mean, variance, autocorrelation) are constant over time.

**A time series model cannot be built unless the time series is stationary.**

### Three Criteria for Stationarity

| Criterion | Description |
|-----------|-------------|
| **Constant Mean** | The mean of the series should not be a function of time |
| **Constant Variance** | The variance should not be a function of time (homoscedasticity) |
| **Constant Autocorrelation** | The covariance between the i-th and (i+m)-th term depends only on the lag m, not on time |

---

## Testing for Stationarity

### Method 1: Rolling Statistics
- Plot the **moving average** or **moving variance** (e.g., over the last 12 months at each time t)
- If these vary significantly with time → non-stationary

### Method 2: ADF Test (Augmented Dickey-Fuller)

> Tests for the presence of a **unit root** in the series.

| Hypothesis | Statement |
|------------|-----------|
| **H₀ (Null)** | The series has a unit root (non-stationary) |
| **H₁ (Alternate)** | The series has no unit root (stationary) |

**Decision rule:** Reject H₀ if:
- Test statistic < Critical Value (compare signed values, not absolute)
- p-value < significance level (e.g., 0.05)

**Output:** Test statistic, p-value, critical values at 1%, 5%, 10% confidence intervals.

---

### Method 3: KPSS Test (Kwiatkowski-Phillips-Schmidt-Shin)

> Figures out if a time series is stationary around a mean or linear trend, or non-stationary due to a unit root.

| Hypothesis | Statement |
|------------|-----------|
| **H₀ (Null)** | The data is **trend stationary** |
| **H₁ (Alternate)** | The data is **not** trend stationary |

**Decision rule:** Reject H₀ if p-value < significance level (e.g., 0.05).

---

### Combining ADF and KPSS Results

| ADF Result     | KPSS Result    | Conclusion                                     |
| -------------- | -------------- | ---------------------------------------------- |
| Non-stationary | Non-stationary | **Series is not stationary**                   |
| Stationary     | Stationary     | **Series is stationary**                       |
| Non-stationary | Stationary     | **Trend stationary** → remove trend first      |
| Stationary     | Non-stationary | **Difference stationary** → apply differencing |

> Always apply **both tests** for reliable conclusions.

---

##  Eliminating Trend and Seasonality

### Method 1: Differencing
> Taking the difference of observation at time t with the observation at t–1.

$$Y_t = Y_t - Y_{t-1}$$

One of the most common methods to deal with both trend and seasonality.

### Method 2: Decomposition
> Model trend and seasonality **separately**, then remove them from the series to return the remaining (residual) component.

**Goal:** Remove the series' dependence on time and stabilize the mean so trend and seasonality are reduced.

> Advanced decomposition techniques can generate better results (e.g., STL decomposition).

---

## ARIMA Model

> **ARIMA** (Auto-Regressive Integrated Moving Averages) — used for series with significant dependence among values.

**Key idea:** ARIMA forecasting for a stationary time series is essentially a **linear equation**. Statistical software identifies the appropriate number of lags or amount of differencing automatically.

### ARIMA Parameters (p, d, q)

| Parameter | Name | Meaning |
|-----------|------|---------|
| **p** | Auto-Regressive (AR) terms | Number of lag values of the dependent variable used as predictors |
| **d** | Integrated (I) — Differencing | Number of non-seasonal differences applied to make the series stationary |
| **q** | Moving Average (MA) terms | Number of lagged forecast errors used in prediction |

**Example — p = 5:** Predictors for x(t) are x(t–1), x(t–2), ..., x(t–5)

**Example — q = 5:** Predictors for x(t) are e(t–1), ..., e(t–5), where e(i) = difference between moving average at i-th instant and actual value

---

### Determining p and q

**Use two plots:**

| Plot | Description | Use For |
|------|-------------|---------|
| **ACF** (Autocorrelation Function) | Correlation between the time series and a lagged version of itself | Determining **q** (MA terms) |
| **PACF** (Partial Autocorrelation Function) | Correlation between the time series and a lagged version, after removing effects already explained by intervening lags | Determining **p** (AR terms) |

---

## Performance Measures

| Metric | Formula | Notes |
|--------|---------|-------|
| **MAE** (Mean Absolute Error) | Average of \|forecast error\| | All errors treated equally |
| **MSE** (Mean Squared Error) | Average of (forecast error)² | Penalizes large errors more heavily |
| **RMSE** (Root Mean Squared Error) | √MSE | Same units as original data; easier to interpret |

> **When to use:** RMSE is most common for time series as it keeps errors in the original unit and penalizes large deviations more than MAE does.

---
# Sequential Pattern Mining - Lecture  9

---

## What is Sequential Pattern Mining?

- Identifies **frequently occurring ordered events or subsequences** as patterns
- A **sequence** is an ordered list of symbols, formally defined as $S = \{s_1, s_2, s_3, \ldots, s_n\}$
- Items that occur together form **itemsets**; sequences are ordered lists of itemsets

---

## Applications

- Finding frequently occurring patterns
- Comparing sequences
- Finding missing sequence items
- Building efficient indexes for sequence information

### Real-world use cases
- Customer shopping sequences
- Medical treatments
- Natural disasters
- Telephone calling patterns
- Sequences of locations visited by vehicles
- Word patterns in text (NLP)

---

## Types of SPM

| Type | Description | Examples |
|------|-------------|---------|
| **String Mining** | Limited character sets | DNA sequences (A, T, C, G); ASCII patterns |
| **Itemset Mining** | Patterns in ordered datasets | Marketing & sales (cross-selling, inventory, pricing) |

---

## Key Definitions

### Items and Itemsets
- **Item set $I$**: a set of symbols, e.g. $I = \{a, b, c, d, e\}$
- **Itemset**: a subset of $I$; an item cannot appear more than once
  - e.g. $\{a, b, c\}$ or $\{d, e\}$

### Sequence
$$S = [X_1, X_2, \ldots, X_n] \quad \text{where } X_j \subseteq I$$

- $[\{a,b\}, \{c\}]$ = a, b purchased together, then c purchased later

### Subsequence
$S_A$ is a subsequence of $S_B$ if there exist integers $1 \leq i_1 < i_2 < \ldots < i_r \leq t$ such that $A_1 \subseteq B_{i_1}, A_2 \subseteq B_{i_2}, \ldots$

| Expression                                           | Result |
| ---------------------------------------------------- | ------ |
| $[\{a,c\}] \subseteq [\{a,b,c\}]$                    | True   |
| $[\{a,c\}] \subseteq [\{a\}, \{c\}]$                 | False  |
| $[\{a\}, \{c\}] \subseteq [\{a,b\}, \{d\}, \{b,c\}]$ | True   |
| $[\{a\}, \{c\}] \subseteq [\{a,c\}, \{d\}]$          | False  |

### Support of a Sequence
The **number of sequences** in database $D$ that contain sequence $S_A$.

> [!example] Example Database
> | SID | Sequence |
> |-----|----------|
> | S1 | $\langle\{a,b\},\{c\},\{a\}\rangle$ |
> | S2 | $\langle\{a\},\{b\},\{c\}\rangle$ |
> | S3 | $\langle\{b\},\{c\},\{d\}\rangle$ |
> | S4 | $\langle\{b\},\{a,b\},\{c\}\rangle$ |
>
> - $\text{Sup}[\{a\}] = 3$ → S1, S2, S4
> - $\text{Sup}[\{b\}] = 4$ → S1, S2, S3, S4
> - $\text{Sup}[\{a,b\}] = 2$ → S1, S4 *(same itemset)*
> - $\text{Sup}[\{a\},\{b\}] = 3$ → S1, S2, S4 *(a then b in sequence)*

### Sequential Pattern
- **Input**: Sequence database $D$ and minimum support threshold $\text{minsup} > 0$
- **Output**: All sequences $S$ where $\text{sup}(S) \geq \text{minsup}$

---

## Challenges

- Huge number of possible sequential patterns hidden in databases
- Algorithm must:
  - Find the **complete set** of patterns satisfying minimum support
  - Be **efficient and scalable** with few database scans
  - Support **user-specific constraints**

---

## Methods for SPM

```
SPM Methods
├── Apriori-based Approaches
│   ├── GSP (Generalized Sequential Pattern) — horizontal data
│   └── SPADE — vertical data
└── Pattern-Growth-based Approaches
    ├── FreeSpan
    └── PrefixSpan ← fastest in benchmarks
```

> [!tip] Performance
> PrefixSpan > SPADE > FreeSpan > GSP in terms of runtime efficiency at scale.

---

## GSP Algorithm (Apriori-Based)

### Core Principle — Apriori Property
> If a sequence $S$ is **not frequent**, then **none of its super-sequences** is frequent.
> e.g., if $\langle hb \rangle$ is infrequent → $\langle hab \rangle$ and $\langle (ah)b \rangle$ are also infrequent.

### Two-Step Process
1. **Join Step**: Generate candidate $k$-sequences ($C_k$) by joining $L_{k-1}$ with itself
2. **Prune Step**: Use the Apriori property to eliminate infrequent candidates

### Key Rule for Joining
- $\{ab\} \neq \{ba\}$ → **order matters** for sequences across itemsets
- $\{(a,b)\} = \{(b,a)\}$ → **order doesn't matter** within an itemset

---

## GSP Worked Example

> [!example] Sequence Database (minsup = 2)
> | SID | Sequence |
> |-----|----------|
> | 1 | $\langle\{a,b\},\{c\},\{f,g\},\{g\},\{e\}\rangle$ |
> | 2 | $\langle\{a,d\},\{c\},\{b\},\{a,b,e,f\}\rangle$ |
> | 3 | $\langle\{a\},\{b\},\{f,g\},\{e\}\rangle$ |
> | 4 | $\langle\{b\},\{f,g\}\rangle$ |

### Step 1 — 1-length frequent sequences (drop $\{d\}$, support = 1)
$\{a\}:3,\ \{b\}:4,\ \{c\}:2,\ \{e\}:3,\ \{f\}:4,\ \{g\}:3$

### Step 2 — 2-length frequent sequences (minsup ≥ 2)
$\{ab\}:2,\ \{ac\}:2,\ \{ae\}:3,\ \{af\}:3,\ \{ag\}:2,\ \{(a,b)\}:2$
$\{be\}:3,\ \{bf\}:4,\ \{bg\}:3$
$\{ce\}:2,\ \{cf\}:2$
$\{fe\}:2,\ \{(f,g)\}:3,\ \{ge\}:2$

### Step 3 — 3-length frequent sequences
$\{abe\}:2,\ \{abf\}:2,\ \{ace\}:2,\ \{acf\}:2,\ \{afe\}:2$
$\{a(f,g)\}:2,\ \{age\}:2,\ \{bfe\}:2,\ \{b(f,g)\}:3,\ \{bge\}:2,\ \{(f,g)e\}:2$

### Step 4 — 4-length frequent sequences
$\{a(f,g)e\}:2,\ \{b(f,g)e\}:2$
*(e.g., $\{abf\} + \{bfe\} \rightarrow \{abfe\}$ but support = 1, pruned)*

---

## SPM vs Association Rule Mining

| | Association Rules | Sequential Patterns |
|--|--|--|
| **Order** | Not considered | Order is essential |
| **Use case** | Co-occurrence | Temporal/ordered patterns |
| **Example** | {bread, butter} bought together | bed → mattress → pillows over time |

> [!quote] Key insight
> "5% of customers buy bed first, then mattress, then pillows." Items are not purchased at the same time — they follow a sequence.

---

## Sequential Rules

### Types
1. **Standard Sequential Rules**
2. **Partially-Ordered Sequential Rules**

### Partially-Ordered Sequential Rules
A rule $X \rightarrow Y$ where:
- $X$ and $Y$ are itemsets (order within each set doesn't matter)
- If items in $X$ occur, they will be followed by items in $Y$

### Evaluation Metrics

| Metric | Formula / Meaning |
|--------|------------------|
| **Support** | Number of sequences containing $X$ followed by $Y$ |
| **Confidence** | $P(Y \mid X) = \frac{\text{Support}(X \rightarrow Y)}{\text{Support}(X)}$ |
| **Lift** | $> 1$ = positive association; $A$ increases likelihood of $B$ |
| **Conviction** | $> 1$ = strong dependence of $X$ on $Y$ |
| **Zhang's Metric** | $+1$ = strong positive; $-1$ = negative/avoidance; $\approx 0$ = no association |

> [!example]
> Rule $\{a\} \rightarrow \{e,f\}$:
> - **Support** = 3 (appears in seq1, seq2, seq3)
> - **Confidence** = 1.0 (100%) — every time $a$ appears, $e$ and $f$ follow

---
# Network Analysis - Lecture 10
---
# Network Analysis & Graph Data Structures

> [!info] Overview
> A **network** (also called a **graph** in mathematics) is a structure representing a group of objects/people and the relationships between them. It consists of **nodes** and **edges**.

## Tags
#data-mining #network-analysis #graph-theory #social-network-analysis #centrality

---

## What is a Network?

- **Nodes** → represent the objects/entities being analyzed
- **Edges** → represent the relationships between those objects
- Can model social networks, biological systems, transportation systems, and more

---

## Applications

### General Uses
- Understanding the structure of relationships in social networks
- Analyzing natural phenomena (change processes)
- Studying biological systems of organisms

### Specific Tasks
- Identifying the most influential person/people in a group
- Defining characteristics of groups of users
- Predicting suitable items for users (recommendations)

### Real-world Examples

| Example | Nodes | Edges |
|---------|-------|-------|
| **Social Media (Facebook)** | Users | Friendships, group memberships |
| **Flight Routes** | Airports | Flight connections |
| **Disease Transmission** | People/organisms | Contact/transmission events |
| **Food Chain** | Species | Predator-prey relationships |
| **Retweet Networks** | Twitter users | Retweet relationships |

---

## Basic Structure of a Network

### Key Elements

**Nodes**
- Individual entities in the network
- Can be people, computers, neurons, companies, etc.

**Edges**
- Represent relationships/connections between nodes
- Can be **directed** (one-way) or **undirected** (two-way)
- The number of edges connected to a node = **degree** of that node

**Network Topology**
- Overall shape/structure of the network
- Types:
  - **Regular** — every node has the same number of connections
  - **Random** — edges formed randomly between nodes
  - **Scale-free** — some nodes have far more connections than others

**Clusters / Communities**
- Groups of nodes more densely connected with each other than with the rest of the network
- Important for understanding network behavior and subgroup dynamics

**Centrality Measures**
- Metrics that identify the most important nodes
- Based on degree, closeness to other nodes, or bridging role between groups

---

## Network Analysis Techniques

| Technique | Description |
|-----------|-------------|
| **Centrality Measures** | Identify the most important nodes (degree, betweenness, eigenvector centrality) |
| **Community Detection** | Find clusters/communities (Louvain method, Girvan-Newman method) |
| **Network Modeling** | Model how networks form and grow (e.g., Barabási–Albert model for scale-free networks) |
| **Network Dynamics** | Study how networks change over time (nodes/edges added or removed, community evolution) |

---

## Centrality Metrics

> [!note] Goal
> Measuring **Network Centrality** = identifying the most important/influential node in a network (e.g., the most influential person in a social group).

### Types of Centrality

**Degree Centrality**
- Simply the **number of edges** a node has
- Higher degree → higher centrality

**Eigenvector Centrality**
- Extends degree by considering the **centrality of neighboring nodes**
- The eigenvector corresponding to the **highest eigenvalue** of the adjacency matrix represents node centrality
- A node connected to many *highly connected* nodes ranks higher

**Betweenness Centrality**
- Based on **shortest paths**
- Counts how many shortest paths between any two nodes pass *through* node $i$
- High betweenness = a "bridge" connecting different parts of the network

**Closeness Centrality**
- Finds nodes with the **smallest average distance** to all other nodes
- Based on the length of the path from node $i$ to all other nodes
- High closeness = can quickly reach the rest of the network

### Summary Table

| Centrality | What it measures | High value means... |
|---|---|---|
| Degree | # of direct connections | Many direct neighbors |
| Eigenvector | Connection quality | Connected to well-connected nodes |
| Betweenness | Bridging role | Key intermediary/connector |
| Closeness | Average distance to others | Can spread info quickly |

---

## Python Implementation

### Basic Network with NetworkX

```python
import networkx as nx
import matplotlib.pyplot as plt

# Create undirected graph
G = nx.Graph()

# Add nodes and edges
G.add_nodes_from([1, 2, 3, 4, 5])
G.add_edges_from([(1,2), (1,3), (2,3), (3,4), (4,5), (2,5)])

# Draw
nx.draw(G, with_labels=True, node_color='lightblue',
        node_size=1000, font_size=12, font_weight='bold')
plt.title('Network Analysis Diagram')
plt.show()

# Performance metrics
print("Number of nodes:", G.number_of_nodes())
print("Number of edges:", G.number_of_edges())
print("Avg clustering coefficient:", nx.average_clustering(G))
print("Diameter (longest shortest path):", nx.diameter(G))
```

### Computing All Centrality Measures

```python
# Degree centrality
for k, v in sorted(nx.degree_centrality(G).items(), key=lambda x: -x[1]):
    print(f"{k}: {v:.3f}")

# Eigenvector centrality
for k, v in sorted(nx.eigenvector_centrality(G).items(), key=lambda x: -x[1]):
    print(f"{k}: {v:.3f}")

# Betweenness centrality
for k, v in sorted(nx.betweenness_centrality(G).items(), key=lambda x: -x[1]):
    print(f"{k}: {v:.3f}")

# Closeness centrality
for k, v in sorted(nx.closeness_centrality(G).items(), key=lambda x: -x[1]):
    print(f"{k}: {v:.3f}")
```

> [!example] Sample Output (11-node graph A–K)
> ```
> degree centrality:    C:0.3  D:0.3  G:0.3  H:0.3 ...
> eigenvector centrality: G:0.481  D:0.443  C:0.405 ...
> betweenness centrality: H:0.6  G:0.578  I:0.378 ...
> closeness centrality:   G:0.5   H:0.476  D:0.435 ...
> ```

---

## Social Network Analysis (SNA)

> A research method used to **visualize and analyze relationships and connections** between entities within a network.

- Nodes = individuals or entities
- Edges = relationships (communication, collaboration, competition)

### Example: Friend Group Network (Alice, Bob, Carol, David, Eve)

```python
G = nx.Graph()
G.add_nodes_from(['Alice','Bob','Carol','David','Eve'])
G.add_edges_from([('Alice','Bob'), ('Bob','Carol'),
                  ('Carol','David'), ('David','Eve'), ('Eve','Alice')])
```

- All nodes have degree centrality = 0.5 (2 edges each in a cycle)
- Betweenness centrality = 0.167 for all (symmetric ring)

### Degree in SNA

Nodes with **higher degree** = more connected individuals  
Nodes with **higher betweenness** = gatekeepers / bridge connectors between communities

---

## Key Terminology Quick Reference

| Term | Definition |
|------|-----------|
| **Node / Vertex** | An entity in the network |
| **Edge / Link** | A relationship between two nodes |
| **Degree** | Number of edges connected to a node |
| **Directed graph** | Edges have direction (one-way) |
| **Undirected graph** | Edges are bidirectional |
| **Diameter** | Longest shortest path in the network |
| **Clustering coefficient** | How interconnected a node's neighbors are |
| **Scale-free network** | A few nodes (hubs) have many more connections than others |

---
# Naïve Bayes — Additional Examples

> [!info] Overview
> Worked examples of the **Naïve Bayes classifier** applied to text classification. Uses **Laplace smoothing** to handle zero-probability issues.

## Tags
#machine-learning #naive-bayes #text-classification #probability

---

## Core Formula

$$P(\text{class} \mid \text{document}) \propto P(\text{class}) \times \prod_{w \in d} P(w \mid \text{class})$$

With **Laplace (add-1) smoothing**:

$$P(w \mid \text{class}) = \frac{\text{count}(w, \text{class}) + 1}{\text{total words in class} + |V|}$$

where $|V|$ is the vocabulary size.

---

## Example 1 — Chinese vs. Japanese

### Training Data

| Doc | Words | Class |
|-----|-------|-------|
| 1 | Chinese Beijing Chinese | c |
| 2 | Chinese Chinese Shanghai | c |
| 3 | Chinese Macao | c |
| 4 | Tokyo Japan Chinese | j |
| **5 (Test)** | Chinese Chinese Chinese Tokyo Japan | **?** |

**Vocabulary**: Chinese, Beijing, Shanghai, Macao, Tokyo, Japan → $|V| = 6$

---

### Step 1 — Compute Priors

$$P(c) = \frac{3}{4}, \quad P(j) = \frac{1}{4}$$

---

### Step 2 — Compute Conditional Probabilities (with Laplace smoothing)

**Class $c$ (Chinese):** total word count = 5 (Beijing:1, Macao:1, Chinese:5) → 8 tokens
$$P(\text{Chinese} \mid c) = \frac{5+1}{8+6} = \frac{6}{14}$$
$$P(\text{Tokyo} \mid c) = \frac{0+1}{8+6} = \frac{1}{14}$$
$$P(\text{Japan} \mid c) = \frac{0+1}{8+6} = \frac{1}{14}$$

**Class $j$ (Japanese):** total word count = 3 tokens
$$P(\text{Chinese} \mid j) = \frac{1+1}{3+6} = \frac{2}{9}$$
$$P(\text{Tokyo} \mid j) = \frac{1+1}{3+6} = \frac{2}{9}$$
$$P(\text{Japan} \mid j) = \frac{1+1}{3+6} = \frac{2}{9}$$

---

### Step 3 — Classify Test Document 5

Test: *Chinese Chinese Chinese Tokyo Japan*

$$P(c \mid d_5) = \frac{3}{4} \times \frac{6}{14} \times \frac{6}{14} \times \frac{6}{14} \times \frac{1}{14} \times \frac{1}{14} \approx \mathbf{0.0003012}$$

$$P(j \mid d_5) = \frac{1}{4} \times \frac{2}{9} \times \frac{2}{9} \times \frac{2}{9} \times \frac{2}{9} \times \frac{2}{9} \approx \mathbf{0.000135}$$

> [!success] Result
> $P(c \mid d_5) > P(j \mid d_5)$ → **Classified as Chinese (c)**

---

## Example 2 — Sports vs. Not Sports

### Training Data

| Doc | Words | Class |
|-----|-------|-------|
| 1 | A great game | sports |
| 2 | The election was over | not sports |
| 3 | Very clean match | sports |
| 4 | A clean but forgettable game | sports |
| 5 | It was a close election | not sports |
| **6 (Test)** | A very close game | **?** |

**Vocabulary**: A, great, game, the, election, was, over, very, clean, match, but, forgettable, it, close → $|V| = 14$

---

### Step 1 — Compute Priors

$$P(\text{sports}) = \frac{3}{5}, \quad P(\text{not sports}) = \frac{2}{5}$$

---

### Step 2 — Compute Conditional Probabilities

**Total word counts:**
- Sports docs (1, 3, 4): 3 + 3 + 5 = **11 tokens**
- Not Sports docs (2, 5): 4 + 5 = **9 tokens**

| Word | $P(\text{word} \mid \text{sports})$ | $P(\text{word} \mid \text{not sports})$ |
|------|------|------|
| a | $\frac{2+1}{11+14} = \frac{3}{25}$ | $\frac{1+1}{9+14} = \frac{2}{23}$ |
| very | $\frac{1+1}{11+14} = \frac{2}{25}$ | $\frac{0+1}{9+14} = \frac{1}{23}$ |
| close | $\frac{0+1}{11+14} = \frac{1}{25}$ | $\frac{1+1}{9+14} = \frac{2}{23}$ |
| game | $\frac{2+1}{11+14} = \frac{3}{25}$ | $\frac{0+1}{9+14} = \frac{1}{23}$ |

---

### Step 3 — Classify Test Document 6

Test: *A very close game*

$$P(\text{sports} \mid d_6) = \frac{3}{5} \times \frac{3}{25} \times \frac{2}{25} \times \frac{1}{25} \times \frac{3}{25} \approx \mathbf{0.00002764}$$

$$P(\text{not sports} \mid d_6) = \frac{2}{5} \times \frac{2}{23} \times \frac{1}{23} \times \frac{2}{23} \times \frac{1}{23} \approx \mathbf{0.000005717}$$

> [!success] Result
> $P(\text{sports} \mid d_6) > P(\text{not sports} \mid d_6)$ → **Classified as Sports**

---

*Tags: #feature-selection #PCA #linear-regression #logistic-regression #data-analytics #data-preprocessing #data-mining #similarity #dissimilarity #proximity #cosine-similarity #jaccard #euclidean #text-analytics #NLP #sentiment-analysis #TF-IDF #bag-of-words #naive-bayes #SVM #random-forest
