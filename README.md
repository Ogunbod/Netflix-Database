# Netflix-Database

 ### Project Overview

 
Creation of MySQL database for a movie rental and subscription service like Netflix. The service has movies, subscribers, and movie rentals. Each movie has details like movie ID, title, director, genre, and release year. Subscribers have details like subscriber ID, name, email, subscription plan, and subscription date. Movie rentals include details such as rental ID, movie ID, subscriber ID, rental date, and return date.
Tasks Done:
 - Designing the database schema for these entities.
 - Writing SQL queries for actions like adding a new movie, subscribing a new user, renting a movie to a subscriber, and returning a movie.
 - Constructing complex queries to generate reports like most popular movies, active subscribers, movies rented by a particular subscriber, and total rentals in a specific period.

 ### Data Source

 ### Tool
 - SQL Server- Data Analysis

 ### Data Creation
 
 In the intial data preparation phase, we performed the following tasks:
1. Database creation.
2. Inserting each table headers 
3. Adding necessary details to each tables
4. Creation of Primary keys and Foerign Keys
5. Querying the Dataset

### Data Analysis
Including some interesting codes/features worked on
```sql
create database netflix;
use netflix;

create table netflix (
movies varchar (45) not null,
subscribers varchar (45) not null,
movie_rentals varchar (45));

create table movie (
movie_id int primary key not null,
title varchar (45) not null,
director varchar (45) not null,
genre varchar (45) not null,
release_year date not null);

insert into movie values
(901, 'Vertigo', 'chuan_wan', 'action', '1987-08-24'),
(902,  'The_Innocents','gutter','action', '1962-02-19' ),
(903, 'Lawrence_of_Arabia','james', 'action', '1962-12-11'),
(904,  'The_Deer_Hunter','david', 'horror', '1979-03-08' ),
(905,  'Amadeus', 'gutter','acction','1985-01-07'),
(906, 'Blade_Runner','jude', 'sci-fi_action', '1982-09-09'),
(907,  'Eyes_Wide_Shut','gutter','acction','1986-01-07'), 
(908,  'The_Usual_Suspects','wilder', 'crime', '1995-08-25'), 
(909, 'Chinatown','jackie_chan', 'action', '1974-08-09'),
(910,  'Boogie_Nights','david', 'horror', '1998-02-16'),
(911, 'Annie_Hall','david', 'horror', '1977-04-20'),
(912,  'Princess_Mononoke','jude', 'sci-fi_action',  '2001-10-19'), 
(913,  'The_Shawshank_Redemption', 'jude', 'sci-fi_action','1995-02-17'),
(915,  'Titanic', 'titan', 'romance','1998-01-23' ),
(916,  'Good_Will_Hunting','gutter','acction', '1999-06-03'),
(917,  'Deliverance', 'jude', 'sci-fi_action', '1982-10-05' ),
(918,  'Trainspotting','jude', 'sci-fi_action', '1996-02-23'), 
(919,  'The_Prestige','jude', 'sci-fi_action',  '2006-11-10');


create table subscribers (
subscriber_id int primary key not null,
name varchar (45) not null,
email varchar (45) not null,
subscription_plan int not null,
subscription_date date not null);

create table movie_rentals(
rental_id int primary key not null,
movie_id int, foreign key (movie_id) references movie (movie_id),
subscriber_id int, foreign key (subscriber_id) references subscribers (subscriber_id),
rental_date date not null,
return_date date not null);
```

 
