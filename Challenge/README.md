# Algorithmic Trading Challenge

The analyst assumed the role of a financial advisor at one of the top five financial advisory firms in the world. The firm constantly competes with the other major firms to manage and automatically trade assets in a highly dynamic environment. In recent years, the firm has heavily profited by using computer algorithms that can buy and sell faster than human traders.

The speed of these transactions gave the firm a competitive advantage early on. But, people still need to specifically program these systems, which limits their ability to adapt to new data. The analyst is planning to improve the existing algorithmic trading systems and maintain the firm’s competitive advantage in the market. To do so, they will enhance the existing trading signals with machine learning algorithms that can adapt to new data.

## Baseline Model Tuning and Results:

### Baseline Model: SVM model
- 3 months training data
- Short window = 4, long window = 100

    ![baseline_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/baseline_perf.png)

    ![baseline_cumu_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/baseline_cumu_returns.png)

### Tuned Baseline Model: SVM model, 6 Months Training Data
- 6 months training data
- Short window = 4, long window = 100

    ![6mo_baseline_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/6mo_baseline_perf.png)

    ![6mo_baseline_cumu_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/6mo_baseline_cumu_returns.png)

### Tuned Baseline Model: SVM model, 12 Months Training Data
- 6 months training data
- Short window = 4, long window = 100

    ![12mo_baseline_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/12mo_baseline_perf.png)

    ![12mo_baseline_cumu_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/12mo_baseline_cumu_returns.png)

The analyst can note that changing the size of the training data set by increasing the month value for the training end variable does little to improve effectiveness of the model.  One can see small increases in accuracy as the month value increases, but the recall for -1.0 decreases.

### Tuned Baseline Model: SVM model, Short Window = 10, Long Window = 200
- 3 months training data
- Short window = 10, long window = 200

    ![SW10_LW200_baseline_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/SW10_LW200_baseline_perf.png)

    ![SW10_LW200_baseline_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/SW10_LW200_baseline_returns.png)

### Tuned Baseline Model: SVM model, Short Window = 2, Long Window = 50
- 3 months training data
- Short window = 2, long window = 50

    ![SW2_LW50_baseline_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/SW2_LW50_baseline_perf.png)

    ![SW10_LW200_baseline_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/SW2_LW50_baseline_returns.png)

### Tuned Baseline Model: SVM model, Short Window = 50, Long Window = 100
- 3 months training data
- Short window = 50, long window = 100

    ![SW10_LW200_baseline_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/SW50_LW100_baseline_perf.png)

    ![SW10_LW200_baseline_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/SW50_LW100_baseline_returns.png)

### Tuned Baseline Model: SVM model, 6 months of Training Data, Short Window = 10, Long Window = 200
- 6 months training data
- Short window = 10, long window = 200

    ![optimized_baseline_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/optimized_baseline_perf.png)

    ![6mo_SW10_LW200_baseline_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/6mo_10SW_200LW_baseline_cumu_returns.png)

The analyst can also note that changing the size of the short and long windows does little to improve the effectiveness of the model.  As the window values increase, one can see small increases in accuracy and recall for the -1.0, however the recall for the 1.0 slightly decreases.  It was concluded that the most optimal model used 6 months of training data, a short window of 10, and a long window of 200.  This resulted in a high accuracy score relative to the baseline, as well as, high recall on the 1.0, and the highest recall of any of the tuned models on the -1.0.

## New Machine Learning Classifiers and Results:

The analyst ran the same data set through various other classifiers to evaluate model performance.  The classifier typers were LogisticRegression, DecisionTreeClassifier, and AdaBoost.  The results from those models are shown below:

### Logistic Regression Model: 6 months of Training Data, Short Window = 10, Long Window = 200
- 6 months training data
- Short window = 10, long window = 200

    ![LR_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/LR_perf.png)

    ![LR_cumu_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/LR_cumu_returns.png)

### Decision Trees Model: 6 months of Training Data, Short Window = 10, Long Window = 200
- 6 months training data
- Short window = 10, long window = 200

    ![DT_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/DT_perf.png)

    ![DT_cumu_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/DT_cumu_returns.png)

### AdaBoost Model: 6 months of Training Data, Short Window = 10, Long Window = 200
- 6 months training data
- Short window = 10, long window = 200

    ![Ada_perf.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/Ada_perf.png)

    ![Ada_cumu_returns.png](https://github.com/hillmanj1995/Module-14-Algorithmic-Trading/blob/main/Challenge/Resources/Ada_cumu_returns.png)

The analyst noted that the additional models that utilized new methods of classifiers did not outperform the optimized baseline model.  It was observed that the Logistic Regression, Decision Trees, and AdaBoost models all had high recall values for the -1.0, which was not noted in the baseline models, however the accuracy scores of these models were lower than that of the optimized baseline model.