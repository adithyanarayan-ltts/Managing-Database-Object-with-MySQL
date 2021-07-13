###  Advanced Queries using 2 tables
1. Write the query to display productionid, production name with total number movies produced by each.

    Ans. ```select productions.Productionid, Productionname, count(Productionname) as count from movie inner join productions where productions.Productionid=movie.Productionid group by movie.Productionid order by movie.Productionid;```
    
    ![](/Images/AS1.PNG)

2. Write the query to display production name, owner name have produced more than 2 movies.

    Ans. select Productionname, Ownername, Moviename from movie Inner Join productions on movie.Productionid=productions.Productionid group by Productionname having count(Productionname)>2;

    ![](/Images/AS2.PNG)

3. Write the query to display production name, owner name have produced maximum movies

    Ans. select Productionname, Ownername, Moviename from movie Inner Join productions on movie.Productionid=productions.Productionid group by Productionname having count(Productionname)=(select count(productionid) as count from movie group by productionid order by count(productionid) desc limit 1);
    ![](/Images/AS3.PNG)

4. Write the query to display the moviename, heroname and productionname acted in the producer name= ’Subaskaran’.

    Ans. select Moviename, Heroname, Productionname from movie Inner Join productions on movie.Productionid=productions.Productionid where Ownername = "Subaskaran";

    ![](/Images/AS4.PNG)

5. Write the query to display the moviename, heroname whose productionid ends with 82.
    
    Ans. select Moviename, Heroname from movie where Productionid like "%82";

    ![](/Images/AS5.PNG)
6. Write the query to display the productionname, ownername who has not produced the movie.
    
    Ans. select productions.productionid, count(movie.productionid) from productions left join movie on productions.productionid=movie.productionid group by productions.productionid;

    ![](/Images/AS6.PNG)

7. Write the query to display the productionname, ownername who has not produced the ‘hindi’ movie.

    Ans. select distinct productionname, ownername from productions inner join movie on productions.productionid=movie.productionid where language!="Hindi";

    ![](/Images/AS7.PNG)

8. Write the query name to display the heroinename who acted in the different productions but not in same production id.
    
    Ans: select heroine from movie group by heroine having count(distinct movie.productionid)>1;

    ![](/Images/AS8.PNG)

9. Write the query to display the heroname who acted in maximum languages.
    
    Ans: select Heroname from movie group by Heroname order by count(language) desc limit 1;

    ![](/Images/AS9.PNG)

10. Write the query to display the production name, owner name who has produced movie for more languages.
    
    Ans. select Productionname, Ownername from productions inner join movie on productions.productionid = movie.productionid group by Productionname having count(distinct language)>1;

    ![](/Images/AS10.PNG)

11. Write the query to display the productionname, producername who has not produced any movie.
    
    Ans. select Productionname, Ownername from productions left join movie on productions.productionid=movie.productionid group by productionname having count(movie.productionid)=0;

    ![](/Images/AS11.PNG)