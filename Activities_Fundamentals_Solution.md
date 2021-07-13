### Solve the SQL fundamental queries

1.	Display the name of movies, movie type is starts with Drama.
    
    Ans. Select Moviename, Movietype from movie where Movietype like “Drama%”;

    ![](/Images/S1.PNG)
2.	Display the movies acted by actor Ayushmann.

    Ans. Select * from movie where Heroname = “Ayushmann”;

    ![](/Images/S2.PNG)

3.	Display the count of movies, having length above 18.
    
    Ans. Select count(*) from movie where Length>18;	
    
    ![](/Images/S3.PNG)

4.	Display the movie having minimum length.

    Ans. Select * from movie where Length = (Select min(Length) from movie);

    ![](/Images/S4.PNG)
    
5.	Display all the details of movie, the language that first name starts with ‘T’

    Ans. Select * from movie where Language like “T%”;

    ![](/Images/S5.PNG)
    
6.	Display the movie name, hero name, heroine name whose having maximum length.
    
    Ans. Select Moviename, Heroname, Heroine from movie where Length = (Select max(Length) from movie);

    ![](/Images/S6.PNG)
    
7.	Display the movie name, hero name, heroine name the movie released after 15 march 2018.

    Ans. select Moviename, Heroname, Heroine from movie where Releasedate>'2018-03-15';
    
    ![](/Images/S7.PNG)
    
8.	Display the count of thriller movies.

    Ans. select count(*) from movie where Movietype like "%Thriller%";

    ![](/Images/S8.PNG)
    
9.	Display the count of movies whose released before 15 march 2018.

    Ans. select count(*) from movie where Releasedate<'2018-03-15';

    ![](/Images/S9.PNG)
    
10.	 Display the release date of the movie name ‘Zero’.
    
     Ans. select Releasedate from movie where Moviename = "Zero"; 
     
     ![](/Images/S10.PNG)
11.	Display the actor name that acted with ‘Amy’.
    
    Ans. select Heroname from movie where Heroine = "Amy";

    ![](/Images/S11.PNG)
    
12.	Display the Count of maximum movies released in a month of October.

    Ans. select count(*) from movie where Releasedate like '____-10-__';

    ![](/Images/S12.PNG)
    
13.	Display the movienames whose production id is same for different languages.
    
    Ans. 
