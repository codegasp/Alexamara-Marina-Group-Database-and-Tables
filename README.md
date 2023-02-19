CREATE DATABASE ALEXAMARA;

USE ALEXAMARA;

CREATE TABLE Marina
(Marina_Num CHAR(4) PRIMARY KEY,
Name CHAR(20),
Address CHAR(15),
City CHAR(15),
State CHAR(2),
Zip CHAR(5) );

CREATE TABLE Marina_Slip
(SlipID DECIMAL(4,0) PRIMARY KEY,
Marina_Num CHAR(4),
Slip_Num CHAR(4),
Length DECIMAL(4,0),
Rental_Fee DECIMAL(8,2),
Boat_Name CHAR(50),
Boat_Type CHAR(50),
Owner_Num CHAR(4) );

CREATE TABLE Owner
(Owner_Num CHAR(4) PRIMARY KEY,
Last_Name CHAR(50),
First_Name CHAR(20),
Address CHAR(15),
City CHAR(15),
State CHAR(2),
Zip CHAR(5) );

CREATE TABLE Service_Category
(Category_Num DECIMAL(4,0) PRIMARY KEY,
Category_Description CHAR(255) );

CREATE TABLE Service_Request
(Service_ID DECIMAL(4,0) PRIMARY KEY,
Slip_ID DECIMAL(4,0),
Category_Num DECIMAL(4,0),
Description CHAR(255),
Status CHAR(255),
Est_Hours DECIMAL(4,2),
Spent_Hours DECIMAL(4,2),
Next_Service_Date DATE );

INSERT INTO Marina
VALUES
('1','Alexamara East','108 2nd Ave','Brinman','FL','32273');
INSERT INTO Marina
VALUES
('2','Alexamara Central','283 Branston','W Brinman','FL','32274');
INSERT INTO Marina_Slip
VALUES
(1,'1','A1',40,3800.00,'Anderson II','Sprite 4000','AN75');
INSERT INTO Marina_Slip
VALUES
(2,'1','A2',40,3800.00,'Our Toy','Ray 4025','EL25');
INSERT INTO Marina_Slip
VALUES
(3,'1','A3',40,3600.00,'Escape','Sprite 4000','KE22');
INSERT INTO Marina_Slip
VALUES
(4,'1','B1',30,2400.00,'Gypsy','Dolphin 28','JU92');
INSERT INTO Marina_Slip
VALUES
(5,'1','B2',30,2600.00,'Anderson III','Sprite 3000','AN75');
INSERT INTO Marina_Slip
VALUES
(6,'2','1',25,1800.00,'Bravo','Dolphin 25','AD57');
INSERT INTO Marina_Slip
VALUES
(7,'2','2',25,1800.00,'Chinook','Dolphin 22','FE82');
INSERT INTO Marina_Slip
VALUES
(8,'2','3',25,2000.00,'Listy','Dolphin 25','SM72');
INSERT INTO Marina_Slip
VALUES
(9,'2','4',30,2500.00,'Mermaid','Dolphin 28','BL72');
INSERT INTO Marina_Slip
VALUES
(10,'2','5',40,4200.00,'Axxon II','Dolphin 40','NO27');
INSERT INTO Marina_Slip
VALUES
(11,'2','6',40,4200.00,'Karvel','Ray 4025','TR72');
INSERT INTO Owner
VALUES
('AD57','Adney','Bruce and Jean','208 Citrus','Bowton','FL','31313');
INSERT INTO Owner
VALUES
('AN75','Anderson','Bill','18 Wilcox','Glander Bay','FL','31044');
INSERT INTO Owner
VALUES
('BL72','Blake','Mary','2672 Commodore','Bowton','FL','31313');
INSERT INTO Owner
VALUES
('EL25','Elend','Sandy and Bill','462 Riverside','Rivard','FL','31062');
INSERT INTO Owner
VALUES
('FE82','Feenstra','Daniel','7822 Coventry','Kaleva','FL','32521');
INSERT INTO Owner
VALUES
('JU92','Juarez','Maria','8922 Oak','Rivard','FL','31062');
INSERT INTO Owner
VALUES
('KE22','Kelly','Alyssa','5271 Waters','Bowton','FL','31313');
INSERT INTO Owner
VALUES
('NO27','Norton','Peter','2811 Lakewood','Lewiston','FL','32765');
INSERT INTO Owner
VALUES
('SM72','Smeltz','Becky and Dave','922 Garland','Glander Bay','FL','31044');
INSERT INTO Owner
VALUES
('TR72','Trent','Ashton','922 Crest','Bay Shores','FL','30992');
INSERT INTO Service_Category
VALUES
(1,'Routine engine maintenance');
INSERT INTO Service_Category
VALUES
(2,'Engine repair');
INSERT INTO Service_Category
VALUES
(3,'Air conditioning');
INSERT INTO Service_Category
VALUES
(4,'Electrical systems');
INSERT INTO Service_Category
VALUES
(5,'Fiberglass repair');
INSERT INTO Service_Category
VALUES
(6,'Canvas installation');
INSERT INTO Service_Category
VALUES
(7,'Canvas repair');
INSERT INTO Service_Category
VALUES
(8,'Electronic systems (radar, GPS, autopilots, etc.)');
INSERT INTO Service_Request
VALUES
(1,1,3,'Air conditioner periodically stops with code indicating low coolant level. Diagnose and repair.','Technician has verified the problem. Air conditioning specialist has been called.','4','2','2013-07-12');
INSERT INTO Service_Request
VALUES
(2,5,4,'Fuse on port motor blown on two occasions. Diagnose and repair.','Open','2','0','2013-07-12');
INSERT INTO Service_Request
VALUES
(3,4,1,'Oil change and general routine maintenance (check fluid levels, clean sea strainers etc.).','Service call has been scheduled.','1','0','2013-07-16');
INSERT INTO Service_Request
VALUES
(4,1,2,'Engine oil level has been dropping drastically. Diagnose and repair.','Open','2','0','2013-07-13');
INSERT INTO Service_Request
VALUES
(5,3,5,'Open pockets at base of two stantions.','Technician has completed the initial filling of the open pockets. Will complete the job after the initial fill has had sufficient time to dry.','4','2','2010-07-13');
INSERT INTO Service_Request
VALUES
(6,11,4,'Electric-flush system periodically stops functioning. Diagnose and repair.','Open','3','0','2020-12-31');
INSERT INTO Service_Request
VALUES
(7,6,2,'Engine overheating. Loss of coolant. Diagnose and repair.','Open','2','0','2013-07-13');
INSERT INTO Service_Request
VALUES
(8,6,2,'Heat exchanger not operating correctly.','Technician has determined that the exchanger is faulty. New exchanger has been ordered.','4','1','2013-07-17');
INSERT INTO Service_Request
VALUES
(9,7,6,'Canvas severely damaged in windstorm. Order and install new canvas.','Open','8','0','2013-07-16');
INSERT INTO Service_Request
VALUES
(10,2,8,'Install new GPS and chart plotter.','Scheduled','7','0','2013-07-17');
INSERT INTO Service_Request
VALUES
(11,2,3,'Air conditioning unit shuts down with HHH showing on the control panel.','Technician not able to replicate the problem. Air conditioning unit ran fine through multiple tests. Owner to notify technician if the problem recurs.','1','1','2020-12-31');
INSERT INTO Service_Request
VALUES
(12,4,8,'Both speed and depth readings on data unit are significantly less than the owner thinks they should be.','Technician has scheduled appointment with owner to attempt to verify the problem.','2','0','2013-07-16');
INSERT INTO Service_Request
VALUES
(13,8,2,'Customer describes engine as making a clattering sound.','Technician suspects problem with either propeller or shaft and has scheduled the boat to be pulled from the water for further investigation.','5','2','2013-07-12');
INSERT INTO Service_Request
VALUES
(14,7,5,'Owner accident caused damage to forward portion of port side.','Technician has scheduled repair.','6','0','2013-07-13');
INSERT INTO Service_Request
VALUES
(15,11,7,'Canvas leaks around zippers in heavy rain. Install overlap around zippers to prevent leaks.','Overlap has been created. Installation has been scheduled.','8','3','2013-07-17');
UPDATE Service_Request
SET Next_Service_Date = Null
WHERE Next_Service_Date = '2020-12-31';
