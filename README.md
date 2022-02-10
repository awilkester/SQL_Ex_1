# SQL_Ex_1

Create a database - “Digital Career Institute”
rename it to dci
Hint: Use ALTER DATABASE command with RENAME TO.
Create  four schemas  - “students”, “courses”, “partners”,  “sales”
Create at least two tables in each schema, and fill each with at least four rows.
use all DDL commands in some way from your choice
CREATE
ALTER
DROP
TRUNCATE
RENAME

CREATE DATABASE Digitial_Career_Institute;
ALTER DATABASE Digitial_Career_Institute RENAME TO dci;

\c dci

CREATE SCHEMA students;
CREATE SCHEMA courses;
CREATE SCHEMA partners;
CREATE SCHEMA sales;

SET SEARCH_PATH TO public, students, courses, partners, sales;

CREATE TABLE students.favorites (student_name varchar(80), teacher_name varchar(80), subject_name varchar(80));
CREATE TABLE students.least_favorites(student_name varchar(80), teacher_name varchar(80), subject_name varchar(80));

INSERT INTO students.favorites VALUES ('Alex', 'Trish', 'Gym'), ('Gary', 'Fred', 'Math'), ('Mary', 'Fred', 'Physics'), ('Zelda', 'Gawen', 'Stage Acting');
INSERT INTO students.least_favorites VALUES ('Alex', 'Greg', 'History'), ('Gary', 'Greg', 'Zoology'), ('Mary', 'Greg', 'Cosmology'), ('Zelda', 'Greg', 'Basket Weaving');

CREATE TABLE courses.data (teacher_name varchar(80), num_of_students int);
CREATE TABLE courses.location (building_name varchar(80), floor int);

INSERT INTO courses.data VALUES ('Greg', 11), ('Trish', 5), ('Fred', 20), ('Gawen', 19);
INSERT INTO courses.location VALUES ('Hildebrant Court', 0), ('Valley Chamber', 4), ('Presentation Room', 7), ('Simple Closet', 21);

CREATE TABLE partners.address (name varchar(80), street_name varchar(80), street_number int);
CREATE TABLE partners.location (name varchar(80), location point);

INSERT INTO partners.address VALUES ('Harry', 'Gamey Street', 6), ('Larry', 'Thimble Road',  3), ('Barry', 'Too Good To Be True', 20), ('Carey', 'Wreckage Lane', 98);
INSERT INTO partners.location VALUES  ('Harry', '(-71,12)'), ('Larry', '(-69,11)'), ('Barry', '(-73,14)'), ('Carey', '(-71,17)');

CREATE TABLE sales.salespeople (name varchar(80), sales_commission_cap int, sales_ytd money);
CREATE TABLE sales.clients (name varchar(100), salesperson_assigned varchar(80), current_contract money);

INSERT INTO sales.salespeople VALUES ('Julia', 1000000, 371134), ('Tulla', 1000000, 498142), ('Junior', 100000, 99123), ('Kate', 1000000, 817412);
INSERT INTO sales.clients VALUES ('Green Pastures', 'Tulla', 200000), ('Yellow Cliff', 'Tulla', 175000), ('Twilight Market', 'Julia', 75000), ('Media Maven', 'Kate', 315000);

ALTER TABLE sales.salespeople RENAME TO salespeoples;
DROP TABLE sales.salespeoples;
TRUNCATE TABLE partners.location;
