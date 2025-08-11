# Coffee-Shop-Expansion-Analysis-SQL

create database Monday_Coffee;

DROP TABLE IF EXISTS sales;                         
DROP TABLE IF EXISTS customers;                     
DROP TABLE IF EXISTS products;                      
DROP TABLE IF EXISTS city;                       

-- Import Rules                            
-- 1st import to city                           
-- 2nd import to products                            
-- 3rd import to customers                       
-- 4th import to sales                  

CREATE TABLE city                                        
(                                
	city_id	INT PRIMARY KEY,                                     
	city_name VARCHAR(15),	                                       
	population	BIGINT,                                          
	estimated_rent	FLOAT,                                            
	city_rank INT                               
);                            

CREATE TABLE customers                                           
(                                    
	customer_id INT PRIMARY KEY,	                                    
	customer_name VARCHAR(25),	                              
	city_id INT,                                     
	CONSTRAINT fk_city FOREIGN KEY (city_id) REFERENCES city(city_id)                           
);                                    


CREATE TABLE products                                         
(                                        
	product_id	INT PRIMARY KEY,                                
	product_name VARCHAR(35),	                                     
	Price float                           
);                              


CREATE TABLE sales                                  
(                          
	sale_id	INT PRIMARY KEY,                                
	sale_date	date,                                
	product_id	INT,                             
	customer_id	INT,                                    
	total FLOAT,                                      
	rating INT,                             
	CONSTRAINT fk_products FOREIGN KEY (product_id) REFERENCES products(product_id),                                    
	CONSTRAINT fk_customers FOREIGN KEY (customer_id) REFERENCES customers(customer_id)                                         
);                      


### Questions for analysis
-- Q.1 Coffee Consumers Count                  
-- How many people in each city are estimated to consume coffee, given that 25% of the population does?                 

-- Q.2 Total Revenue from Coffee Sales                       
-- What is the total revenue generated across all cities in the last quarter of 2023?                                      

-- Q.3 Sales Count for Each Product                   
-- How many units of each coffee product have been sold?
 
-- Q.4 Average Sales Amount per City                 
-- What is the average sales amount per customer in each city?                       
 
-- -- Q.5 City Population and Coffee Consumers (25%)                
-- Provide a list of cities along with their populations and estimated coffee consumers.                     
-- return city_name, total current cx, estimated coffee consumers (25%)

 -- Q6 Top Selling Products by City                        
-- What are the top 3 selling products in each city based on sales volume?

-- Q.7 Customer Segmentation by City                     
-- How many unique customers are there in each city who have purchased coffee products?

-- Q.8 Average Sale vs Rent                                
-- Find each city and their average sale per customer and avg rent per customer

-- Q.9 Monthly Sales Growth                
-- Sales growth rate: Calculate the percentage growth (or decline) in sales over different time periods (monthly)                
-- by each city

-- Q.10 Market Potential Analysis                              
-- Identify top 3 city based on highest sales, return city name, total sale, total rent, total customers, estimated coffee consumer







