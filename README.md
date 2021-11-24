# DB_ExamPreparation
ExamPreparation for Data Bases
////////////////


Code SQL ///


EXAM Preparation :
CREATE DB AIRPORT.
Planes contains information about the planes.
Flights contains information about the flights. Etc, Passengers, LuggageTypes, 
Each Flight has a name. Each Luggage has a luggage type. 
Each ticket has a passenger, 
Each ticket has a flight, Each ticket has a luggage.

////
--CREATE DATABASE Airport
--USE Airport
CREATE TABLE Planes(
Id INT PRIMARY KEY IDENTITY,
[Name] VARCHAR(30) NOT NULL, 
Seats INT NOT NULL, 
[Range] INT NOT NULL
)

USE Airport
CREATE TABLE Flights(
Id INT PRIMARY KEY IDENTITY,
DepartureTime DATETIME2,
ArrivalTime DATETIME2,
Origin VARCHAR(50) NOT NULL,
Destination VARCHAR(50) NOT NULL,
PlaneId INT FOREIGN KEY REFERENCES Planes(Id) NOT NULL)


CREATE TABLE Passengers(
Id INT PRIMARY KEY IDENTITY,
FirstName VARCHAR(30) NOT NULL,
LastName VARCHAR(30) NOT NULL,
Age INT NOT NULL, 
Address VARCHAR (30) NOT NULL, 
PassportId CHAR(11) NOT NULL
)

CREATE TABLE LuggageTypes(
Id INT PRIMARY KEY IDENTITY, 
[Type] VARCHAR(30) NOT NULL
)


CREATE TABLE Luggages(
Id INT PRIMARY KEY IDENTITY,
LuggageTypeId INT FOREIGN KEY REFERENCES LuggageTypes(Id) NOT NULL,
PassengerId INT FOREIGN KEY REFERENCES Passengers(Id) NOT NULL
)

CREATE TABLE Tickets(
 Id INT PRIMARY KEY IDENTITY,
 PassengerId INT FOREIGN KEY REFERENCES Passengers(Id) NOT NULL,
 FlightId INT FOREIGN KEY REFERENCES Flights(Id) NOT NULL,
 LuggageId INT FOREIGN KEY REFERENCES Luggages(Id) NOT NULL,
 Price DECIMAL(18, 2) NOT NULL
)

///
