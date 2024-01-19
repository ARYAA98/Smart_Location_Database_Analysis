# Smart_Location_Database_Analysis

## Overview
This Jupyter Notebook, `SmartLocation_Database_Analysis.ipynb`, is an analysis of the Smart Location Database from the U.S Environmental Protection agency and the US general Services Administration . The notebook includes exploratory data analysis, data visualization, and statistical modeling to derive insights from the dataset.

## Project Structure
'Smart_location_Database_Analysis.ipynb ' is the main file where the analysis is conducted. The steps include Data Loading, Data preprocessing , Data exploration and Visualization.

## About the Dataset.
The Dataset was downloaded from the US government data : https://data.gov/
The direct link for data : https://catalog.data.gov/dataset/smart-location-database1
The dataset was quite large  and hence could not be uploaded to the Github. Please visit the link for the Dataset.

## Python Packages Used
 The following Python Packages are used in the Project.
 1. pandas : for data manipulation and analysis.
 2. numpy : for numerical operations on arrays and matrices.
 3. matplotlib.pyplot : for creating visualizations
 4. seaborn : for creating visualizations

## Data Sources
- Smart Location Database: /content/drive/MyDrive/EPA_SmartLocationDatabase_V3_Jan_2021_Final.csv

## Requirements and Execution
1. Ensure that python is installed on your system.
2. Clone this repository to your local machine.
3. Install the Python packages listed above.
4. The Jupyter notebook can be run on IDE like Jupyter Lab / Jupyter notebook.Open the Jupyter Notebook in Jupyter Lab or Google Colab.
5. Run the cells in sequence to reproduce the analysis.

## Some Info about the codes :
1. **For reading the Dataset**
   df= pd.read_csv
2. **code for reading the top**
   df.head(10)

3. **for column names, shape , info and statistical info**
   '''python
   df.columns
   df.shape
   df.info()
   df.describe
   '''
5. **For finding null values and dropping null values**
   ''''
   df.isnull().sum()  - giives the number of null values
   df.dropna()        - for dropping null values
   '''

7. **finding unique values in the column**
   df.nunique()
   
8. **For PIE chart**
   '''python
   plt.figure(figsize=(5,5))                                                                 #figure size
   plt.pie(Land_df.values, labels=labels, autopct='%1.1f%%', startangle=140)                 #for plotting pie chart
   plt.title('Land Categories Distribution')                                                 #title of pie chart
   plt.axis('equal')                                                                         
   plt.show()
   '''

   The land_df is the dataframe used for creating pie chart.
   
10. **For scatter plot** 
    '''python
    plt.figure(figsize=(5,5))
    sns.scatterplot(x='TotPop', y='TotEmp', data=Smart_location_df)            # scatter plot
    plt.xlabel('Population Density')
    plt.ylabel('Employment Density')
    plt.title('Population vs Employment Density')
    plt.show()
    '''
    This code takes the Totpop and TotEmp from the smart location df and created a scatter plot.

12. **For Bar chart**
    '''python
   fig = px.bar(employment_density_df, x=employment_density_df.index, y=employment_density_df.values, title='Employment density distribution in 5 tier scheme')
   fig.update_xaxes(title_text='Employment type')
   fig.update_yaxes(title_text='Number ')
   fig.show()
   '''

   The first line of the code selects the values from the dataframe, creates plot and the next two lines gives name to the x and y axis.

11. **Heatmap**
   '''python
   sns.heatmap(Smart_location_df[['AutoOwn0', 'AutoOwn1']].corr(), annot=True, cmap='coolwarm')
   plt.title('Correlation Matrix Heatmap')
   plt.show()
   '''

   This is for creating a heatmap, with annotation .

11. **t-test**
    '''
    from scipy import stats
    t_stat, p_value = stats.ttest_ind(population_density, residential_density, nan_policy='omit')
    print(f"T-statistic: {t_stat}, P-value: {p_value}")
    '''
   
   

