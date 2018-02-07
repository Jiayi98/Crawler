import csv
import urllib
import requests
from bs4 import BeautifulSoup



start_url = "https://movie.douban.com/tag/#/?sort=S&range=9,10&tags=电影"

response = requests.get(start_url)

# This method to get a list of movies from the corresponding category and location
def getMovies(category,location):
        # to create a list to store each movie with its information
        movies_container[]
        # use for loop to get movies from every location
        for element in location:
            html = getHtml(category,element)
            soup = BeautifulSoup(html, "html.parser")
            content = soup.find(id='content').find(class_='list-wp')
            # use for loop to get all information from every url of each movie in current location
            for link in content.findAll('a'):
                name = link.find(class_='title').string
                rate = link.find(class_='rate').string
                info = link.get('href')
                cover = link.find('img').get('src')
                # to create new data from Movie class and store it into the list
                movie = Movie(name,rate,element,category,info,cover)
                movies_container.append(movie)
                
         return movies_container
         
# This method is to get the html of each movie through the given url
def getHtml(category,location):
     url = getMovieUrl(category, location)
     return expanddouban.getHtml(url,True)
  
# This method is to get the url of corresponding category and location.
def getMovieUrl(category, location):
       url = start_url + ",{},{}".format(category,location)
       return url
       
# write a class Movie
class Movie:
  def __init__(self, name,rate,location,category,info_link,cover_link):
        self.name = name
        self.rate = rate
        self.location = location
        self.category = category
        self.info_link = info_link
        self.cover_link = cover_link
        
  # to get all attributes of Movie
  def get_data(self):
        return "{},{},{},{},{},{}".format(self.name,self.rate,self.location,
                                            self.category,self.info_link,self.cover_link)
    
 
