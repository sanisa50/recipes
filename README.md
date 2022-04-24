# About:
This python script reads the recipes and extracts every recipe that has “Chilies” as one of the ingredients. 
This code allows for mispelling of the word for example Chiles as well as the singular form of the word. This part is done using pandas and Fuzzy matching.
FuzzyWuzzy has, just like the Levenshtein package, a ratio function that computes the standard Levenshtein distance similarity ratio between two sequences.

The Levenshtein distance is a metric to measure how apart are two sequences of words. In other words, it measures the minimum number of edits that you need to do to change a one-word sequence into the other. These edits can be insertions, deletions or substitutions. 

The fuzzywuzzy package has a module called process that allows you to calculate the string with the highest similarity out of a vector of strings. 

process.extract() finds best matches in a list or dictionary of choices, return a list of tuples containing the match and it's score.
process.extractOne() is a convenient method which returns the single best choice. 

Additional details about the package can be found [here](https://pypi.org/project/fuzzywuzzy/)

It adds an extra field to each of the extracted recipes with the name difficulty. The difficulty field would have a value of "Hard" if the sum of prepTime and cookTime is greater than 1 hour, "Medium" if the total is between 30 minutes and 1 hour, "Easy" if the total is less than 30 minutes, and "Unknown" otherwise. The resulting dataset is saved as a assortedRecipes.csv file.

For this a fucntion has been created which extract the numerical part and dimensional part from the cookTime and prepTime column. The numerical values are converted into minutes based on the dimensional part.

The the conditions are defined to categories the totalTime into various diffiulty levels using np.select()


## Instructions on how to run:
1. Go to [Google Colab](https://colab.research.google.com/)
2. Open the jupyter notebook (HelloFresh assignment.ipynb) from Git repo. 
    
    You can do this using one of the below mentioned ways:
   - Select GitHub option to open the notebook and paste the path (https://github.com/sanisa50/recipes.git) of this repository and select the notebook file 
   - OR Download from the GitHub repo and upload the notebook file to colab 
   - OR Copy the contents from notebook file and paste them in the newly created notebook in colab
3. Just hit run in colab (Code documentation is present in the notebook file)
4. Output will be saved as assortedRecipes.csv under Files (Left hand menu). You may have to refresh the files in Colab.

## Python Version:
Default version provided by Google Colab should be fine but just to mention the Python version during my session was 3.7.12
