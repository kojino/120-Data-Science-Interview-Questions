## Statistical Inference (15 questions)

#### 1. In an A/B test, how can you check if assignment to the various buckets was truly random?
  - Plot the distributions of multiple features for both A and B and make sure that they have the same shape. More rigorously, we can conduct a permutation test to see if the distributions are the same.
  - MANOVA to compare different means
#### 2. What might be the benefits of running an A/A test, where you have two buckets who are exposed to the exact same product?
  - Verify the sampling algorithm is random.
#### 3. What would be the hazards of letting users sneak a peek at the other bucket in an A/B test?
  - The user might not act the same suppose had they not seen the other bucket. You are essentially adding additional variables of whether the user peeked the other bucket, which are not random across groups.
#### 4. What would be some issues if blogs decide to cover one of your experimental groups?
  - Same as the previous question. The above problem can happen in larger scale.
#### 5. How would you conduct an A/B test on an opt-in feature? 
  - Ask someone for more details.
#### 6. How would you run an A/B test for many variants, say 20 or more?
  - one control, 20 treatment, if the sample size for each group is big enough.
  - Ways to attempt to correct for this include changing your confidence level (e.g. Bonferroni Correction) or doing family-wide tests before you dive in to the individual metrics (e.g. Fisher's Protected LSD).
#### 7. How would you run an A/B test if the observations are extremely right-skewed?
  - lower the variability by modifying the KPI
  - cap values
  - percentile metrics
  - log transform
  - <https://www.quora.com/How-would-you-run-an-A-B-test-if-the-observations-are-extremely-right-skewed>
#### 8. I have two different experiments that both change the sign-up button to my website. I want to test them at the same time. What kinds of things should I keep in mind?
  - exclusive -> ok
#### 9. What is a p-value? What is the difference between type-1 and type-2 error?
  -   

  - type-1 error: rejecting Ho when Ho is true
  - type-2 error: not rejecting Ho when Ha is true
#### 10. You are AirBnB and you want to test the hypothesis that a greater number of photographs increases the chances that a buyer selects the listing. How would you test this hypothesis?
  - For randomly selected listings with more than 1 pictures, hide 1 random picture for group A, and show all for group B. Compare the booking rate for the two groups.
  - Ask someone for more details.
#### 11. How would you design an experiment to determine the impact of latency on user engagement?
  - The best way I know to quantify the impact of performance is to isolate just that factor using a slowdown experiment, i.e., add a delay in an A/B test.
#### 12. What is maximum likelihood estimation? Could there be any case where it doesn’t exist?
  - A method for parameter optimization (fitting a model). We choose parameters so as to maximize the likelihood function (how likely the outcome would happen given the current data and our model).
  - maximum likelihood estimation (MLE) is a method of [estimating](https://en.wikipedia.org/wiki/Estimator "Estimator") the [parameters](https://en.wikipedia.org/wiki/Statistical_parameter "Statistical parameter") of a [statistical model](https://en.wikipedia.org/wiki/Statistical_model "Statistical model") given observations, by finding the parameter values that maximize the [likelihood](https://en.wikipedia.org/wiki/Likelihood "Likelihood") of making the observations given the parameters. MLE can be seen as a special case of the [maximum a posteriori estimation](https://en.wikipedia.org/wiki/Maximum_a_posteriori_estimation "Maximum a posteriori estimation") (MAP) that assumes a [uniform](https://en.wikipedia.org/wiki/Uniform_distribution_\(continuous\) "Uniform distribution \(continuous\)") [prior distribution](https://en.wikipedia.org/wiki/Prior_probability "Prior probability") of the parameters, or as a variant of the MAP that ignores the prior and which therefore is [unregularized](https://en.wikipedia.org/wiki/Regularization_\(mathematics\) "Regularization \(mathematics\)").
  - for gaussian mixtures, non parametric models, it doesn’t exist
#### 13. What’s the difference between a MAP, MOM, MLE estima\- tor? In which cases would you want to use each?
  - MAP estimates the posterior distribution given the prior distribution and data which maximizes the likelihood function. MLE is a special case of MAP where the prior is uninformative uniform distribution.
  - MOM sets moment values and solves for the parameters. MOM is not used much anymore because maximum likelihood estimators have higher probability of being close to the quantities to be estimated and are more often unbiased.
#### 14. What is a confidence interval and how do you interpret it?
  - For example, 95% confidence interval is an interval that when constructed for a set of samples each sampled in the same way, the constructed intervals include the true mean 95% of the time.
  - if confidence intervals are constructed using a given confidence level in an infinite number of independent experiments, the proportion of those intervals that contain the true value of the parameter will match the confidence level.
#### 15. What is unbiasedness as a property of an estimator? Is this always a desirable property when performing inference? What about in data analysis or predictive modeling?
  - Unbiasedness means that the expectation of the estimator is equal to the population value we are estimating. This is desirable in inference because the goal is to explain the dataset as accurately as possible. However, this is not always desirable for data analysis or predictive modeling as there is the bias variance tradeoff. We sometimes want to prioritize the generalizability and avoid overfitting by reducing variance and thus increasing bias.
