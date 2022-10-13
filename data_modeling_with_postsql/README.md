#Sparkify#

  A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app.
  They want to analysis the most commn songs ,the most active users etcetera... ,so as data engineering I should create schema and ETL piplines to optimize this queries.

#sql_queries.py#

  ##contain helper sql statments to create fact and
 dimension tables  and insert data in etl.py##
 
     1-drop
     2-create
     3-insert
     
#create_tables#

  ##Help in executing queries to create schema##
  
     1-connect to database
     2-create cursor
     3-execute queries
     
#etl.py#

  ##extratct ,transform and load data##
  
    ###process_song_file###
    
       It helps in extracting data from song files and inserting it into databases.
    ###process_log_file###
       It helps in extracting data from log files and inserting it into databases.
       
#Tables of schema#

  ##Fact table#
  
    ###songPlay###
    
      column1:songplay_id
      column2:start_time
      column3:user_id
      column4:level
      column5:song_id
      column6:artist_id
      column7:session_id
      column8:location
      column9:user_agent
      
  ##Dimension tables##
  
    ###users###
      column1:user_id
      column2:first_name
      column3:last_name
      column4:gender
      column5:level
    ###songs###
      column1:song_id
      column2:title
      column3:artist_id
      column4:year
      column5:duration
     ###artists###
      column1:srtists_id
      column2:name
      column3:location
      column4:latitude
      column5:longitude
     ###time###
      column1:start_time
      column2:hour
      column3:day
      column4:week
      column5:month
      column6:year
      column7:weekday
      
#Python Script#
    
 ##To run etl.py or create_tables.py ##
 
   ###Open terminal and write ###
   
    python etl.py 
    python create_tables.py 

#Extra Queries#

 ##Most favorite artist##
 
   (%sql select artists.name ,count(songs.song_id) as num_of_songs,artists.artist_id from artists join songs on artists.artist_id=songs.artist_id group     by(artists.artist_id)\
    order by num_of_songs desc \
    limit(2))
  

