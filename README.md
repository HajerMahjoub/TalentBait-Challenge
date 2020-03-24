![](.//media/image8.png){width="1.495738188976378in"
height="0.4218755468066492in"}

**[Text Classifier]{.underline}**

[ ]{.underline} Interview Challenge

Candidate : Hajer Mahjoub

Data Science Engineer Student

At ESPRIT Tunis

1.  **[Exploratory data analysis :]{.underline}**

-   Libraries: seaborn ,json ,pandas ,matplotlib

-   Notebook : TalentBait\_EDA.ipynb

-   The dataset source is a JSON file composed of 10 000 sentence
    > labeled

<!-- -->

-   Labels :

> "soft" ,"tech","none"

-   Number of text per label :

> ![](.//media/image1.png){width="4.234375546806649in" height="2.625in"}

-   The distribution of the number of words in text column :

![](.//media/image5.png){width="4.010416666666667in"
height="2.5833333333333335in"}

The most of the text are within 400 characters with some outliers up to
900 characters long

-   Boxplot :

![](.//media/image9.png){width="5.864583333333333in"
height="3.8645833333333335in"}

> So we delete the long text
>
> ![](.//media/image6.png){width="5.802083333333333in"
> height="3.8645833333333335in"}

-   We can see that, although the length distribution of our data is
    > close similar to each category even that once we are creating the
    > features with TF-IDF scoring, we will normalize the features to
    > keep this distribution

<!-- -->

-   **Dimensionality Reduction :**

<!-- -->

-   Notebook : TalentBait\_ DimensionalityReduction.ipynb

-   We\'ll perform a dimensionality reduction technique to plot the
    observations in 2 dimensions

1.  **Principal Component Analysis :**

![](.//media/image10.png){width="4.65625in"
height="3.4427088801399823in"}

2.  **t-distributed Stochastic Neighbour Embedding:**

![](.//media/image7.png){width="4.572916666666667in"
height="3.4739588801399823in"}

> We can see that the PCA decomposition works much better on our data.
>
> **2. [Feature Engineering :]{.underline}**

-   Libraries : NLTK , Scikit-Learn , Regular Expression

-   Notebook : TalentBait\_EDA.ipynb

-   Process of feature engineering :

<!-- -->

-   Start by cleaning the text from (signs , special characters )

-   Lemmatization & Stemming

-   Label Encoding

-   Split the train and the test data

-   Text representation :

> Choosing TF-IDF Vectors feature ([[short for term frequency--inverse
> document
> frequency]{.underline}](https://en.wikipedia.org/wiki/Tf%E2%80%93idf))

-   Chi squared test : see unigrams and bigrams most correlated with
    each label :

<!-- -->

-   \'none\' label:

<!-- -->

-   Most correlated unigrams:

gute,standort,deutschland,gmbh,kenntnisse

-   Most correlated bigrams:

ms office,gute kenntnisse

-   \'soft\' label:

<!-- -->

-   Most correlated unigrams:

umgang,sap,office, ms,kenntnisse

-   Most correlated bigrams:

gute kenntnisse,ms office

-   \'tech\' label:

<!-- -->

-   Most correlated unigrams:
    flexibilität,hohe,kenntnisse,teamfähigkeit,arbeitsweise

<!-- -->

-   Most correlated bigrams:

hohes maß,wort schrift

-   save the files

> **[3. Model (Train & Test) :]{.underline}**

-   Notebook : TalentBait\_Model2.ipynb

-   we\'ll try several machine learning classification models in order
    > to find which one performs best on our data.

-   We will try with the following models:

<!-- -->

-   Random Forest

-   Multinomial Naïve Bayes

-   Multinomial Logistic Regression

-   Gradient Boosting

<!-- -->

-   The methodology :

> 1 choose hyperparameters
>
> 2 Search Cross Validation process
>
> 3 Grid Search Cross Validation
>
> 4 Training & Test
>
> 5 Calculate accuracy
>
> Note the prediction classify the text and in addition give the the
> conditional probability of belonging to every label
>
> 6 Reporting the performance of each model and plot the confusion
> matrix to summarize
>
> the performance

**. Confusion Matrix of each model :**

-   **Random Forest**

> ![](.//media/image2.png){width="4.895833333333333in"
> height="3.2031255468066493in"}

-   **Multinomial Naïve Bayes**

> ![](.//media/image4.png){width="4.005208880139983in"
> height="2.9583333333333335in"}

-   **Multinomial Logistic Regression**

> ![](.//media/image3.png){width="6.270833333333333in"
> height="3.4583333333333335in"}

-   The Summary table of performance metrics generated in every model :

  **Model**                         **Training Set Accuracy**   **Test Set Accuracy**
  --------------------------------- --------------------------- -----------------------
  Multinomial Logistic Regression   0.923536                    0.902158
  Multinomial Naïve Bayes           0.917856                    0.893881
  Random Forest                     0.918584                    0.887674

-   I did choose the Multinomial Logistic Regression since it has the
    > highest Test Set Accuracy.

**4. [Prediction and application :]{.underline}**

-   For test the chosen model and classify and Input text

> Two solution were provided :

1.  Notebook : Prediction.ipynb

> You can run the cells and fill the text variable with the Input to
> classify

2.  Notebook : theApplication.ipynb

> Using Dash an Open Source Library i created simple web app with simple
> interface to inter text and get prediction to run the app currently
> just run the cells on the notebook

Note : the app can be optimise and deployed

We can use other methods for representation of the text

There is second methodology for the classification of the text i tried
under the Notebook "TaletBait\_Modeling\_2.ipynb"
