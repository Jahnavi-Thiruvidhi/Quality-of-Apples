# Quality-of-Apples

Here is a summary of the data analysis process and results, broken down into six key points:

1. **Dataset Description**:
   - The dataset contains 9 characteristics of apple quality, including `A_id`, `Size`, `Weight`, `Sweetness`, `Crunchiness`, `Juiciness`, `Ripeness`, `Acidity`, and `Quality`.

2. **Skewness Calculation**:
   - The skewness of the `Sweetness` column is calculated to measure the asymmetry of the data distribution.
   - The skewness of the `Crunchiness` column is also calculated for the same purpose.

3. **Correlation Calculation**:
   - The Pearson correlation between `Ripeness` and `Acidity` is computed to determine the linear relationship between these two variables.
   - Similarly, the Pearson correlation between `Quality` (converted to numeric values) and `Weight` is calculated.

4. **Quality Classification**:
   - The `Quality` column is converted to numeric values (1 for 'good' and 0 for 'bad') for correlation analysis with `Weight`.

5. **Quality Counts**:
   - The number of 'good' and 'bad' quality apples is counted from the dataset.

6. **Submission File Creation**:
   - A JSON file named `submission.json` is created, containing the calculated skewness, correlations, and quality counts.

This summary captures the essence of the analysis and the steps taken to derive the required insights from the dataset.
