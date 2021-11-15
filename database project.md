DROP DATABASE IF EXISTS my_computer_shop;
CREATE DATABASE my_computer_shop;
USE my_computer_shop;

-- COPY AND PAST FROM HERE --
CREATE TABLE categories(
	category_id			INT 			PRIMARY KEY,
    category_name		VARCHAR(50)		NOT NULL
    );
    
CREATE TABLE products(
	product_id			INT				PRIMARY KEY			AUTO_INCREMENT,
	category_id			INT 			NOT NULL,
    product_name		VARCHAR(100) 	NOT NULL,
    item_price			DECIMAL(10,2)	NOT NULL,
    discount			INT				NOT NULL
);

CREATE TABLE orders(
	order_id			INT 			PRIMARY KEY			AUTO_INCREMENT,
    customer_id			int				NOT NULL,
    order_date			DATETIME		NOT NULL,
    card_number			VARCHAR(20)		NOT NULL,
    tax_amount			int				NOT NULL,
    shipping_amount			int				NOT NULL
    );

CREATE TABLE customers(
	customer_id			int				PRIMARY KEY,
    email_address		VARCHAR(90)		NOT NULL,
    password			VARCHAR(90)		NOT NULL,
    first_name			VARCHAR(90)		NOT NULL,
    last_name			VARCHAR(90)		NOT NULL,
    line1				VARCHAR(90) 		NOT NULL,
    line2				VARCHAR(90),
    City				VARCHAR(90)		NOT NULL,
    state				VARCHAR(3)		NOT NULL,
    zip					VARCHAR(15)		NOT NULL,
    phone				VARCHAR(90)		NOT NULL
    );
CREATE TABLE order_items(
	Item_id 			INT 			PRIMARY KEY,
	order_id 			INT 			NULL,
	product_id 			INT 			NULL,
	item_price			float		 	NULL,
	Quantity 			INT 			NULL
);
    
    
INSERT INTO categories(category_id,category_name) VALUES
(1,'memory'),
(2,'cpu'),
(3,'gpu'),
(4,'storage');
    

INSERT INTO products(product_id,category_id,product_name,item_price,discount) VALUES
(1,1,'Corsair Vengeance LPX 16 GB (2 x 8 GB) DDR4',20,102.99),
(2,1,'Corsair Vengeance RGB Pro 16 GB (2 x 8 GB) DDR4',35,109.99),
(3,1,'Crucial Ballistix 16 GB (2 x 8 GB) DDR4',10,87.99),
(4,1,'Corsair Vengeance RGB Pro 32 GB (2 x 16 GB) DDR4',15,226.99),
(5,1,'Crucial 64 GB (1 x 64 GB) Registered DDR4',20,118.99),
(6,1,'G.Skill Aegis 16 GB (2 x 8 GB) DDR4',30,109.99),
(7,1,'G.Skill Aegis 16 GB (2 x 8 GB) DDR4',20,166.66),
(8,1,'G.Skill Trident Z Neo 16 GB (2 x 8 GB) DDR4',20,220.00),
(9,2,'AMD Ryzen 5 3600 3.6 GHz 6-Core Processor',25,253.84),
(10,2,'AMD Ryzen 7 3700X 3.6 GHz 8-Core Processor',70,308.99),
(11,2,'Intel Core i9-10900K 3.7 GHz 10-Core Processor',0,381.02),
(12,2,'AMD Ryzen 9 5900X 3.7 GHz 12-Core Processor',0,150.57),
(13,2,'Intel Xeon E5-2690 V4 2.6 GHz 14-Core Processor',20,249.4),
(14,2,'Intel Core 2 Duo E7300 2.66 GHz Dual-Core OEM/Tray Processor',15,75.35),
(15,2,'AMD Ryzen 7 2700 3.2 GHz 8-Core Processor',50,250.54),
(16,3,'Diamond Radeon HD 5450 1 GB',25,44.99),
(17,3,'NVIDIA TITAN RTX 24 GB ',15,2000.50),
(18,3,'XFX Radeon Pro Duo 8 GB',10,540),
(19,3,'NVIDIA GeForce GTX Titan X 12 GB',15,1200.00),
(20,3,'Gigabyte GeForce RTX 3090 24 GB AORUS MASTER',20,355),
(21,3,'EVGA GeForce RTX 2080 SUPER 8 GB XC ',0,254),
(22,3,'EVGA GeForce RTX 3090 24 GB FTW3',15,370),
(23,4,'Samsung 970 Evo 1 TB M.2-2280 NVME Solid State Drive',15,55.45),
(24,4,'Western Digital Blue SN550 1 TB M.2-2280 NVME Solid State Drive',20,199.99),
(25,4,'Samsung 980 Pro 1 TB M.2-2280 NVME Solid State Drive',15,349.99),
(26,4,'Kingston A400 240 GB 2.5\" Solid State Drive',40,34.99),
(27,5,'Asus TUF GAMING X570-PLUS (WI-FI) ATX AM4 Motherboard',20,37.03),
(28,5,'Gigabyte B450M DS3H V2 Micro ATX AM4 Motherboard',15,400.15);

INSERT INTO orders(order_id,customer_id,order_date,card_number,tax_amount,shipping_amount) VALUES
(1,1,'2019-12-10',5560442614007594,4.54,15.05),
(2,2,'2019-11-09',30148080070049,3.56,10.03),
(3,3,'2020-01-11',2720994678908376,7.05,6.05),
(4,4,'2020-02-25',5560442614007594,7.06,14.47),
(5,5,'2020-04-19',4508058593413096,9.02,12.04),
(6,6,'2020-03-15',2720994678908376,8.04,9.05),
(7,7,'2020-4-11',6398687954658994,9.03,11.23);

INSERT INTO customers VALUES
(1,'arussel@gmail.com','Elitegamer356!','Aiden','Russel','672 Cir dr NW Ave','','Hickory','NC',28601,'(828)-321-9045'),
(2,'kgilbert32@aol.com','iluvFluffle$','Kyler','Gilbert','5832 Roman RD','','Greenville','SC',29605,'(864)-951-6734'),
(3,'lilys@hotmail.com','password123','Lily','Smith','487 Bridle Ave','','Philladelphia','PA',19102,'(267)-821-0946'),
(4,'jwheeler872@gmail.com','Bestprogrammer3','Jack','Wheeler','982 Creekside Dr','','Orlando','FL',32789,'(407)-562-7812'),
(5,'jchristine@yahoo.com','$3cUr3P@$$wORd','Christine','Jones','2341 Marvin St.','','Statesville','NC',28625,'(704)-581-9234'),
(6,'jrivers@aol.com','Thecapitalized1','Johnathan','Rivers','489 W. Center lane','','Gaffney','SC',29340,'(864)-093-6872'),
(7,'sshaw213@yahoo.com','Skii4life!','Sydney','Shaw','342 South Main St.','','Nashville','TN',37011,'(615)-021-4921');
    
INSERT INTO order_items(item_id,order_id,product_id,item_price,quantity) VALUES
(1,3,3,79.19,1),
(2,5,7,133.33,1),
(3,2,28,680,2),
(4,1,5,118.99,1),
(5,10,9,190.38,1),
(6,3,14,75.35,1),
(7,4,12,150.57,1),
(8,9,23,47.13,1),
(9,2,21,508,2),
(10,7,20,284,1),
(11,8,10,308.99,1);
