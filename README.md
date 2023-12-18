# Record Store Project
This project was based on a YouTube [video](https://youtu.be/30W5wjgJR08).

## Exercise
### 1. Creating the environment

Copy the code within the [schema](schema.sql) file, paste it into MySQL Workbench and execute it.
This code will create and enter the database and the tables Bands and Albums.

Next, you should create a table to store all the Songs.
This table should be named `songs` and have four attributes with the following names:

1. `id`: An integer that is the primary key, and auto increments.
2. `name`: A string that cannot be null.
3. `length`: A float that represents the length of the song in minutes that cannot be null.
4. `album_id`: An integer that is a foreign key referencing the albums table that cannot be null.

After successfully creating this table, you can copy the code from [data.sql](data.sql) into MySQL Workbench.
This code will populate the table and fill it with our data so we can get started with our queries!

### 2. Select only the Names of all the Bands

Using an Alias, change the name of the column that returns the data to `Band Name`.
Your query should return something like this:

| Band Name         | 
|-------------------| 
| Seventh Wonder    | 
| Metallica         | 
| The Ocean         | 
| Within Temptation | 
| Death             | 
| Van Canto         | 
| Dream Theater     | 

### 3. Select the Oldest Album

Try to return only one result from this query, and not return any albums that do not have a release year.
This is the oldest album in the data scheme:

| id | name                   | release_year | band_id | 
|----|------------------------|--------------|---------| 
| 5  | ...And Justice for All | 1988         | 2       | 

### 4. Get all Bands that have Albums

There are multiple solutions to this problem, but they will all involve the use of a join.
Return the band name as `Band Name`.

| Band Name         | 
|-------------------| 
| Seventh Wonder    | 
| Metallica         | 
| The Ocean         | 
| Within Temptation | 
| Death             | 
| Van Canto         | 

### 5. Get all Bands that have No Albums

Return the band name as `Band Name`.

| Band Name     | 
|---------------| 
| Dream Theater | 

### 6. Get the Longest Album

Tip: Use an aggregate function.
Return the album name as `Name`, the album release year as `Release Year`, and the album length as `Duration`.

| Name           | Release Year | Duration          | 
|----------------|--------------|-------------------| 
| Death Magnetic | 2008         | 74.76666593551636 | 

### 7. Update the Release Year of the Album with no Release Year

Set the release year to 1986.

If you try to update the release year of a row in MySQL Workbench by using the release_year IS NULL condition in the WHERE statement, you may get an error. This is because MySQL Workbench by default does not allow you to update a table with a primary key without using the primary key in the UPDATE statement. 
This is a good thing, because it prevents you from accidentally updating the wrong row. To avoid this error, make sure to use the primary key of the row you want to update in the WHERE statement of your UPDATE query.

### 8. Insert a record for your favorite Band and one of their Albums

Use a Select to now see that band and album in your tables.

### 9. Delete the Band and Album you added in #8

It is important to delete records in the correct order when an album has a foreign key to a band.

### 10. Get the Average Length of all Songs

Return the average length as `Average Song Duration`.

| Average Song Duration | 
|-----------------------| 
| 5.352472513259112     | 


### 11. Select the longest Song off each Album

Return the album name as `Album`, the album release year as `Release Year`, and the longest song length as `Duration`.

| Album                       | Release Year | Duration | 
|-----------------------------|--------------|----------| 
| Tiara                       | 2018         | 9.5      | 
| The Great Escape            | 2010         | 30.2333  | 
| Mercy Falls                 | 2008         | 9.48333  | 
| Master of Puppets           | 1986         | 8.58333  | 
| ...And Justice for All      | 1988         | 9.81667  | 
| Death Magnetic              | 2008         | 9.96667  | 
| Heliocentric                | 2010         | 7.48333  | 
| Pelagial                    | 2013         | 9.28333  | 
| Anthropocentric             | 2010         | 9.4      | 
| Resist                      | 2018         | 5.85     | 
| The Unforgiving             | 2011         | 5.66667  | 
| Enter                       | 1997         | 7.25     | 
| The Sound of Perseverance   | 1998         | 8.43333  | 
| Individual Thought Patterns | 1993         | 4.81667  | 
| Human                       | 1991         | 4.65     | 
| A Storm to Come             | 2006         | 5.21667  | 
| Break the Silence           | 2011         | 6.15     | 
| Tribe of Force              | 2010         | 8.38333  | 

### 12. Get the number of Songs for each Band

This question is one of the most challenging on the list. It will require you to use a double join to solve it.
Return the band name as `Band`, the number of songs as `Number of Songs`.

| Band              | Number of Songs | 
|-------------------|-----------------| 
| Seventh Wonder    | 35              | 
| Metallica         | 27              | 
| The Ocean         | 31              | 
| Within Temptation | 30              | 
| Death             | 27              | 
| Van Canto         | 32              | 

### Final Script

You can see the solutions and my final script clicking [here](scriptFinal.sql).
Keep in mind that your code may look different from mine, because everyone has their own way of solving problems. If you're interested, feel free to send me a message and we can compare our solutions!
