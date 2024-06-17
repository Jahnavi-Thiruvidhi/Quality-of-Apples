# Quality-of-Apples

Here is a step-by-step breakdown of the results from the code:

1. **Load the dataset**:
   - This step was successful, and the dataset was loaded into a DataFrame.

2. **Calculate the skewness of the `Sweetness` column**:
   ```python
   sweetness_skewness = data['Sweetness'].skew()
   ```
   - The skewness of the `Sweetness` column is calculated.

3. **Calculate the skewness of the `Crunchiness` column**:
   ```python
   crunchiness_skewness = data['Crunchiness'].skew()
   ```
   - The skewness of the `Crunchiness` column is calculated.

4. **Calculate the Pearson correlation between `Ripeness` and `Acidity`**:
   ```python
   ripeness_acidity_corr = data['Ripeness'].corr(data['Acidity'], method='pearson')
   ```
   - The Pearson correlation between `Ripeness` and `Acidity` is calculated.

5. **Calculate the Pearson correlation between `Quality` and `Weight`**:
   ```python
   data['Quality_numeric'] = data['Quality'].apply(lambda x: 1 if x == 'good' else 0)
   quality_weight_corr = data['Quality_numeric'].corr(data['Weight'], method='pearson')
   ```
   - The `Quality` column is converted to a numeric form.
   - The Pearson correlation between the numeric `Quality` and `Weight` is calculated.

6. **Count the number of `good` and `bad` quality apples**:
   ```python
   quality_counts = data['Quality'].value_counts()
   num_good_apple = int(quality_counts.get('good', 0))
   num_bad_apple = int(quality_counts.get('bad', 0))
   ```
   - The number of `good` and `bad` quality apples is counted.

7. **Prepare the results in a JSON format for submission**:
   ```python
   submission = {
       "1.1": round(sweetness_skewness, 4),
       "1.2": round(crunchiness_skewness, 4),
       "1.3": round(ripeness_acidity_corr, 4),
       "1.4": round(quality_weight_corr, 4),
       "1.5": [num_bad_apple, num_good_apple]
   }
   ```

Here are the results from the analysis:

```python
{
    "1.1": 0.1738,  # Skewness of Sweetness
    "1.2": 0.0607,  # Skewness of Crunchiness
    "1.3": -0.2071,   # Pearson correlation between Ripeness and Acidity
    "1.4": 0.0132,   # Pearson correlation between Quality and Weight
    "1.5": [218, 202]  # Number of bad and good quality apples
}
```

With this, you can generate the JSON file using the following code:

```python
import json

# Create the submission dictionary
submission = {
    "1.1": round(sweetness_skewness, 4),
    "1.2": round(crunchiness_skewness, 4),
    "1.3": round(ripeness_acidity_corr, 4),
    "1.4": round(quality_weight_corr, 4),
    "1.5": [num_bad_apple, num_good_apple]
}

# Convert submission to JSON string and print
submission_json = json.dumps(submission, indent=4)
print(submission_json)

