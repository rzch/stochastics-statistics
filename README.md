# Stochastics, Statistics, Skedastics

These are a collection of continuously-evolving notes in probability and
statistics, that I started writing as a graduate student. They begin at
a high-school or early-undergraduate introduction, and then go on to
cover topics mainly from the undergraduate to early-graduate level.\
They may be particularly useful for someone who:

-   is studying probability and statistics from an electrical
    engineering, computer science or econometrics curriculum.

-   wishes to use the notes as a handy reference, that complements other
    resources (much like an encyclopaedia).

-   is a practitioner who wishes to gain deeper theoretical
    understanding in the methods and techniques they use.

-   is interested in the overlaps and connections between different
    fields that apply probability/statistics.

-   wants to use these notes as a model for writing their own collection
    of notes.

While all concepts in probability and statistics aim to be
self-contained, some sections inevitably assume background knowledge and
familiarity with outside topics such as (multivariate) calculus, real
analysis, linear algebra, mathematical optimisation, and systems theory.
Whenever one of these topics is invoked however, we usually refer to
them by their commonly-known names, so that they can be easily looked up
elsewhere. We will also occasionally make forward-references to sections
later in the document, so the notes certainly do not need to be read
strictly in the presented order.\
In writing these notes, the goal was to strike a balance between rigour
and pedagogy. To this end, we aim to motivate, develop intuition, and
highlight connections behind the methods and formulae. At the same time,
we do not shy away from deriving things from first principles or
providing proofs. Occasionally however, when a proof is omitted, it may
be because the result feels intuitive on its own, or perhaps because the
proof is advanced, lengthy or not particularly instructive. We will at
the very least try to explain why a result might hold intuitively or
heuristically. Also as these notes are intended to be viewed digitally,
space constraints are not a main issue, so proof/derivation steps are
sometimes outlined in more detail than what printed textbooks may
allow.\
Etymology:

-   *stochastic* from Greek, meaning to 'aim at' or to 'guess'.

-   *statistic* from Latin, meaning 'of the state/council'.

-   *skedastic* from Greek, meaning 'scattered'.

## Contents
-   [Preface](#preface)
-   [Fundamentals](#fundamentals)
    -   [Introductory Probability](#introductory-probability)
        -   [Probability Laws](#probability-laws)
        -   [Counting](#counting)
        -   [Probability Distributions](#probability-distributions)
        -   [Expectation](#expectation)
        -   [Variance](#variance)
        -   [Independence](#independence)
        -   [Transformations of Random
            Variables](#transformations-of-random-variables)
        -   [Families of Continuous Univariate Probability
            Distributions](#families-of-continuous-univariate-probability-distributions)
        -   [Families of Discrete Univariate Probability
            Distributions](#families-of-discrete-univariate-probability-distributions)
        -   [Distribution Relationships
            [@Leemis2008]](#distribution-relationships)
    -   [Introductory Statistics](#introductory-statistics)
        -   [Data Generating Processes](#data-generating-processes)
        -   [Descriptive Statistics](#descriptive-statistics)
        -   [Normal Statistics](#normal-statistics)
        -   [Inferential Statistics](#inferential-statistics)
        -   [Two-Sample Inference](#sec:two-sample_inference)
        -   [Simple Linear Regression](#sec:simple_linear_regression)
        -   [Design of Experiments](#design-of-experiments)
        -   [Statistical Graphics](#statistical-graphics)
        -   [Method of Moments [@Greene2012]](#sec:method_of_moments)
    -   [Intermediate Probability](#intermediate-probability)
        -   [Random Vectors](#random-vectors)
        -   [Families of Multivariate Probability
            Distributions](#families-of-multivariate-probability-distributions)
        -   [Inequalities in Probability](#inequalities-in-probability)
        -   [Notions of Probabilistic
            Convergence](#notions-of-probabilistic-convergence)
        -   [Moments](#moments)
        -   [Probability Generating
            Functions](#probability-generating-functions)
        -   [Characteristic Functions](#sec:characteristic_functions)
        -   [Cumulants](#cumulants)
        -   [Exponential Families](#sec:exponential_families)
    -   [Intermediate Statistics](#intermediate-statistics)
        -   [Multivariate Statistics](#multivariate-statistics)
        -   [Statistical Decision Theory](#statistical-decision-theory)
        -   [Least Squares](#least-squares)
        -   [Estimation Theory](#estimation-theory)
        -   [Maximum Likelihood
            Estimation](#sec:maximum_likelihood_estimation)
        -   [Maximum Likelihood
            Inference](#maximum-likelihood-inference)
        -   [Multiple Hypothesis Testing](#multiple-hypothesis-testing)
        -   [Generalised Linear Models](#generalised-linear-models)
        -   [Quantile Regression](#quantile-regression)
    -   [Advanced Probability](#advanced-probability)
        -   [Multivariate Gaussian
            Properties](#multivariate-gaussian-properties)
        -   [Stochastic Processes](#stochastic-processes)
        -   [Families of Stochastic
            Processes](#families-of-stochastic-processes)
        -   [Branching Processes](#branching-processes)
        -   [Renewal Theory](#renewal-theory)
        -   [Central Limit Theorems](#sec:central_limit_theorems)
        -   [Concentration Inequalities](#concentration-inequalities)
        -   [Large Deviations Theory](#sec:large_deviations_theory)
        -   [Random Matrices](#sec:random_matrices)
    -   [Bayesian Probability &
        Statistics](#bayesian-probability-statistics)
        -   [Bayes' Theorem Extensions](#bayes-theorem-extensions)
        -   [Bayesian Priors](#bayesian-priors)
        -   [Bayesian Updating](#bayesian-updating)
        -   [Bayesian Inference](#bayesian-inference)
        -   [Posterior Approximations](#sec:posterior_approximations)
        -   [Bayesian Networks](#bayesian-networks)
        -   [Bernstein-von Mises Theorem
            [@Train2009]](#bernstein-von-mises-theorem)
        -   [Cox's Theorem [@Jaynes2003; @Baldi2001]](#coxs-theorem)
        -   [Subjective Probability
            [@Schervish1995; @Hogg2013]](#subjective-probability)
    -   [Markov Processes](#markov-processes)
        -   [Finite-State Discrete-Time Markov
            Chains](#finite-state-discrete-time-markov-chains)
        -   [Infinite-State Discrete-Time Markov
            Chains](#infinite-state-discrete-time-markov-chains)
        -   [Continuous-Time Markov Processes
            [@Anderson1991]](#continuous-time-markov-processes)
        -   [Time-Inhomogeneous Markov
            Chains](#time-inhomogeneous-markov-chains)
        -   [Hidden Markov Models](#sec:hidden_markov_models)
        -   [Markov Decision Processes](#sec:markov_decision_processses)
        -   [Markov Networks](#markov-networks)
        -   [Semi-Markov Chains
            [@Hoek2018; @Pflug1996]](#semi-markov-chains)
        -   [Quasistationary Distributions
            [@Collet2012]](#quasistationary-distributions)
    -   [Measure Theoretic Probability](#measure-theoretic-probability)
        -   [Probability Spaces](#probability-spaces)
        -   [Lebesgue Integration](#lebesgue-integration)
        -   [Radon-Nikodym Derivatives](#radon-nikodym-derivatives)
        -   [Product Measures](#product-measures)
        -   [Convergence of Probability
            Measures](#convergence-of-probability-measures)
        -   [Measure Theoretic Stochastic
            Processes](#measure-theoretic-stochastic-processes)
        -   [Ergodic Theory](#ergodic-theory)
    -   [Advanced Statistics](#advanced-statistics)
        -   [Asymptotic Statistics](#asymptotic-statistics)
        -   [Empirical Measures](#empirical-measures)
        -   [Order Statistics](#sec:order_statistics)
        -   [Computational Statistics](#computational-statistics)
        -   [Resampling Methods](#resampling-methods)
        -   [Survival Analysis](#survival-analysis)
        -   [Nonparametric Statistics](#nonparametric-statistics)
        -   [Robust Statistics](#robust-statistics)
    -   [Stochastic Calculus](#stochastic-calculus)
        -   [Continuity of Stochastic
            Processes](#continuity-of-stochastic-processes)
        -   [Mean-Square Stochastic
            Calculus](#mean-square-stochastic-calculus)
        -   [Continuous-Time Martingales](#continuous-time-martingales)
        -   [Itô Calculus](#itô-calculus)
        -   [Stratonovich Integral](#stratonovich-integral)
        -   [Stochastic Differential
            Equations](#stochastic-differential-equations)
        -   [Malliavin Calculus](#malliavin-calculus)
        -   [Numerical Stochastic Differential
            Equations](#numerical-stochastic-differential-equations)
    -   [Probabilistic Combinatorics](#probabilistic-combinatorics)
        -   [Stirling's Approximation](#stirlings-approximation)
        -   [Inclusion-Exclusion
            Principle](#inclusion-exclusion-principle)
        -   [Pigeonhole Principle](#pigeonhole-principle)
        -   [Partitions](#partitions)
        -   [Catalan Numbers [@Lange2010]](#catalan-numbers)
        -   [Derangements](#derangements)
        -   [Twelvefold Way](#twelvefold-way)
        -   [Probabilisitic Method](#probabilisitic-method)
        -   [Random Graphs](#random-graphs)
-   [Applications](#applications)
    -   [Information Theory](#information-theory)
        -   [Entropy](#sec:entropy)
        -   [Kullback-Leibler
            Divergence](#sec:kullback-leibler_divergence)
        -   [Maximum Entropy Distributions
            [@Grunwald2007]](#maximum-entropy-distributions)
        -   [Coding Theory [@Cover2006]](#coding-theory)
        -   [Information Criteria](#sec:information_criteria)
        -   [Optimal Experimental Design](#optimal-experimental-design)
        -   [Statistical Distances](#statistical-distances)
        -   [Algorithmic Information
            Theory](#algorithmic-information-theory)
        -   [Information Geometry](#information-geometry)
    -   [Econometrics](#econometrics)
        -   [Economic Data](#economic-data)
        -   [Model Specification](#model-specification)
        -   [Regression Analysis](#regression-analysis)
        -   [Instrumental Variables
            Regression](#instrumental-variables-regression)
        -   [Panel Data Regression](#panel-data-regression)
        -   [Time-Series Models](#sec:time-series_models)
        -   [Time-Series Regression](#time-series-regression)
        -   [Time-Series Analysis](#time-series-analysis)
        -   [Time-Series Forecasting](#time-series-forecasting)
        -   [Generalised Method of
            Moments](#generalised-method-of-moments)
    -   [Machine Learning](#machine-learning)
        -   [Concepts in Machine
            Learning](#concepts-in-machine-learning)
        -   [Statistical Classification](#statistical-classification)
        -   [Unsupervised Learning](#unsupervised-learning)
        -   [Artificial Neural Networks](#artificial-neural-networks)
        -   [Gaussian Process Regression](#gaussian-process-regression)
        -   [Ensemble Methods](#ensemble-methods)
        -   [Decision Trees [@James2013]](#decision-trees)
        -   [Dimensionality Reduction](#dimensionality-reduction)
        -   [Statistical Learning Theory](#statistical-learning-theory)
    -   [Statistical Signal Processing](#statistical-signal-processing)
        -   [Random Signals and Systems](#random-signals-and-systems)
        -   [Power Spectral Density](#power-spectral-density)
        -   [Spectral Density Estimation
            [@Stoica2005]](#spectral-density-estimation)
        -   [Linear Filtering](#linear-filtering)
        -   [Kalman Filtering](#kalman-filtering)
        -   [Particle Filtering](#particle-filtering)
        -   [Independent Component Analysis
            [@Hyvaerinen2001; @Theodoridis2015]](#independent-component-analysis)
        -   [Wavelets
            [@Wang2012; @Mallat2009; @Wasserman2006]](#wavelets)
        -   [Compressed Sensing
            [@Foucart2013; @Hastie2015]](#compressed-sensing)
    -   [Stochastic Control](#stochastic-control)
        -   [System Identification](#system-identification)
        -   [Queueing Theory [@Leon-Garcia2008]](#queueing-theory)
        -   [Stochastic Stability](#stochastic-stability)
        -   [Stochastic Games](#stochastic-games)
        -   [Stochastic Dynamic
            Programming](#sec:stochastic_dynammic_programming)
        -   [Stochastic Optimal Control](#stochastic-optimal-control)
        -   [Stochastic Approximation
            [@Spall2003; @Asmussen2007]](#sec:stochastic_approximation)
        -   [Multi-Armed Bandits](#multi-armed-bandits)
        -   [Reinforcement Learning](#reinforcement-learning)
    -   [Quantitative Finance](#quantitative-finance)
        -   [Copulae](#sec:copulae)
        -   [Heavy-Tailed Distributions
            [@Foss2013]](#sec:heavy-tailed_distributions)
        -   [Stochastic Orders](#stochastic-orders)
        -   [Portfolio Optimisation](#portfolio-optimisation)
        -   [Discrete-Time Derivatives Pricing
            [@Blyth2013; @Shreve2004; @Hoek2006]](#discrete-time-derivatives-pricing)
        -   [Continuous-Time Derivatives Pricing
            [@Hull2018; @Wilmott2007; @Neftci2000]](#continuous-time-derivatives-pricing)
        -   [Optimal Stopping](#optimal-stopping)
        -   [Ruin Theory](#ruin-theory)
        -   [Financial Econometrics](#financial-econometrics)
    -   [Physics](#physics)
        -   [Hamiltonian Monte-Carlo
            [@Brooks2011]](#hamiltonian-monte-carlo)
        -   [Statistical Mechanics](#statistical-mechanics)
        -   [Statistical Physics](#statistical-physics)
        -   [Langevin Dynamics](#langevin-dynamics)
        -   [Mean Field Theory](#mean-field-theory)
        -   [Quantum Mechanics
            [@Whittle2000; @Hamming1991; @Williams2001]](#quantum-mechanics)
        -   [Econophysics [@Mantegna1999]](#econophysics)