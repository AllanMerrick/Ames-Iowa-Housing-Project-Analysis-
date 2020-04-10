#### Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Dictionary](#Data-Dictionary)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)
- [Model Score Summaries](#Model-Score-Summaries)
- [Sources](#Sources)

#### Problem Statement
Given the dataset from Kaggle's challenge: [Ames Housing Dataset](#https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/overview), we were tasked with testing and identifying house-features best suited for estimating a house price. Our overall recommendations will err more on advisement side of prioritizing house features as opposed to expecting house price.
<br> <br><t>HoA is suffering because home-owner negligence is driving property value down. Complaints received identified that the HoA's home-value assessments are unfounded thus home-owners are no longer following HoA policies.
<br><br>
The problem we identify here: what can we do to improve our neighborhood's home values during a time of low HoA approval and regulation following.
<br>
We will look at individual feature sets and use regression model scoring to identify influentifial home features. Then we'll compare this with external research to identify best recommendations with influence to improving home price.

#### Executive Summary
Our models showed our single numerical categories to give us the best consistent regression scoring (R2, MRSE, CrossVal). These consisted mostly of room related scorings and quantities. While our Numerical Category Regression model averaged a score of approximately 74% variability explained, it swung a large Root Mean Squared Error of close to 40,000. <br> <br>
Understanding this we can use the numerical R scoring and investigate its correlation to sale price, then find home projects that fall within the individual average home owner's finance. <br> <br> External research confirms we have several means to take wihtin our own personal homes for value improvement as well as legal means to pursue enforcement of architechtural upgrades.

#### Data Dictionary
[Ames Dataset Data Dictionary](#https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/data)

|name|type|description|
|:--|---|--:|
|`testdf` | DataFrame | testing data frame after imputing and/or deleting nan's during cleaning|
| `train` | DataFrame | testing dataframe after imputing and/or deleting nan's during cleaning|
| `testog` | DataFrame | unfiltered, unmodified dataframe for reference|
| `dfv1` | DataFrame | categorical training dataframe|
| `testv1` | DataFrame | categorical testing dataframe|
| `subf#` | DataFrame | dataframe assignment for exporting to csv in Kaggle's requested format|
| `testnm` | DataFrame | numerical test set |
| `numtrain` | DataFrame | numerical train set|
| `testsq` | DataFrame | scaled numerical features formatted from our test dataset|
| `sqtrain` | DataFrame | scaled numerical features formatted from o ur train set|
| `features` | List | Categorical features selected to apply to `train` set.|
| `traincols` | List | Categorical training set includes `'price'` amd `'id'`|
| `testcols` | List | Categorical `test` set that includes and `'id'`|
| `num_feats` | List | Numerical feature set for our `train` dataframe includes `'SalePrice'` and `'Id'`|
| `tnum_feats` | List | Numerical feature set for our `test` dataframe includes `'id'`|
| `sq_feats` | List | Scalable Numeral feature set for our `train` dataframe includes `'SalePrice'` and `'Id'`|
| `tsq_feats` | List | Scalable Numeral feature set for our `test` dataframe includes `'id'`|
| `X, y, and variants` List | DataFrame, Series | These are our regression feature and variable assignments. code blocks will contain descriptions of each.|
| `preds, trainpreds, etc.` List | Series | these are our y_prediction variables established from our model.|
| `tempcols` | list | comprehension for building neighborhood list to compare against test |
| `tempcols2` | list | comprehension for building neighborhood list to compare against train|

#### Conclusions and Recommendations
Currently our model is better suited for finding correlating features rather than predict price. The features we've worked with have been documented and cleaned so we can continue assessing trends and use external data to align with features we deem valuable. <br><br>

While we can maintain our current HoA regulations, our model does help us find features we can investigate on improving or adding to our own houses, increasing their individual value. <br><br>

If we'd like to pursue tightening down on regulations, windows can fall under architectural replacement with the right authorizations. However, this would be costly to us and the community as a whole. As windows are trendy, we can take advantage of recyclable material trend and take installation costs down by finding a specialist from within our community network.

#### Model  Score Summaries:

##### Categorical Score Summary
- `train R2 score`: 0.6578429575225204
- `test R2 score`: 0.5762651698596276
- `cross val score`: 0.6163932809393643
- `R2 Score (without split)`: 0.6455431466231798
- `RMSE Train/Split score`: 46848.294477176525
- `RMSE on full features`: 47592.55017675726

##### Conclusions:
Our training set is definitely overfit, with the cross val and test scores showing .03-.04 difference implies our model has higher variance (test and crossval lower than our training score).

We will proceed to now test numerical features.

##### Numercal Score Summary
- `train R2 score`: 0.7553817990521428
- `test R2 score`: 0.7636609305004238
- `cross val score`: 0.7464907120547879
- `R2 Score (without split)`: 0.7576575430618783
- `RMSE Train/Split score`: 38611.440491748916
- `RMSE on full features`: 39003.28692496293

##### Conclusions:
Numerical columns definitely had a stronger R2 score, the change in test r2 vs cross-val(cv) implies we may be underfit, but with low variance. It's certainly our better model so far


###### Scaled Score Summary
- `train R2 score`: 0.6723902525839343
- `test R2 score`: 0.7294544670268371
- `cross val score`: 0.634384215358273
- `R2 Score (without split)`: 0.6887855968651643
- `RMSE Train/Split score`: 44683.792650829135
- `RMSE on full features`: 44338.90383859943


#### Conclusions:
Adding our scaled data revelead a high variance with the increase in test R2 score. CV scoring implies there may have been some data imbalance with train/split.
<br><br> Our overal r2 sits at a lower .67 with RMSE rising higher than the numericals.



#### Sources
<br> -[Source: Features to Boost Home Value](https://www.realtor.com/news/trends/top-15-home-features-to-boost-your-homes-value-and-sell-it-faster/)
<br> -[Source: Features Buyers Want](https://www.kiplinger.com/slideshow/real-estate/T010-S001-home-features-today-s-buyers-want-most/index.html)
<br> -[Source: Remodeling Costs vs Sale](https://www.remodeling.hw.net/cost-vs-value/2019/west-north-central/)
<br> -[Source: HoA Window Regulations](https://ringerwindows.com/residential-windows-hoa-programs/)
<br> -[Scource: Typical Home Owner](https://www.zillow.com/report/2017/homeowners/typical-american-homeowner/)
