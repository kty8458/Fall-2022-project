# Spider for IMDb top 250 movies
- This package is used to crawl the basic information of the top250 movies on IMDb, and provides data visualization of the global interface and analysis of individual movie data, and able to produce pdf reports.
- To import this package, the user could add the `from spider_tools.Data_Visualization import Data` and the `from spider_tools.movie import Movie` on the begin of code.
### Import the Conda environment
`conda env create -f environment.yaml`
### Introduction of folders  
   1. **data**: There is a .xls file named IMDb.xls in the folder, which is all the information of 250 movies crawled from IMDb  
   2. **movie_chart**: A generate budget and worldwide gross comparison charts based on movies of the one genre will be generated in this folder
   3. **movie_pdf**: A report of one movie will be generated in this folder
   4. **plot_html**: Proportion of films, word frequency, and year of movie which are plotted by *pyechatrs* are saved in this folder
   5. **spider_tools**: This folder include all of the libraries that our team created:  
      1. *spider_IMDb.py*: This package is use to crawled all of the basic information of the 250 movies and save. However, because of the administrator of IMDb website add a detection to judge human or robot, it is not longer to run.
      2. *Data_Visualization.py*: This package is use to do export the global results of 250 movies, and the functions are:
         1. `from spider_tools.Data_Visualization import Data`: Import package
         2. `Data('./data/IMDb.xls')`: Initialize class
         3. `Data.Import()`:  Import data
         4. `Data.Cleaning(data)`:  Clean data, the data getting form the first step should be input, and the cleaned data is the output
         5. `Data.Statistics(clean_data)`: Get five values which need for visualization after data statistics, the cleaned data is input, and it will return a 5 length list which include numbers for different countries, name for different countries,a list of years, a list of era years, amd a list of Quantity per era.
         6. `Data.Visualization(clean_data, Statistics_data)`: The data after `Cleaning()` and `Statistics()` is the input, and it will return 7 visualization plots, which include 1.the Distribution of Country origin 2. Year histogram and distribution 3.Year of movies 4. the top 100 most frequent words 5.the proportion of various types of movie 6.the distribution of movie lengths. 
      3. *movie.py*: This package is use to deal with the information for one movie, and it include:
         1. `from spider_tools.movie import Movie`: Import package
         2. `Movie('./data/IMDb.xls', title)`: To initialize the class, the movie's name should be input
         3. `Movie.match_title()`: To check if the movie is in the 250 movies list, it will return a string to tell user the result
         4. `Movie.print_info()`: Print the basic information for the movie
         5. `Movie.generate_histogram()`: Plot generate budget and worldwide gross comparison charts based on movies of the same genre, the result will be saved in **movie_chart**.
         6. `Movie.output_pdf()`: It will generated a pdf report and saved in **movie_pdf**
   6. **environment.yml**: Conda environment file.
   7. **Introduction.ipynb**: Package tutorial and example.
