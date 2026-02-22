##### **DAX Measures used in this Project:**



1. Total Sales = SUM(Fact\_Orders\[Sales])
   
   ---
2. Total Profit = SUM(Fact\_Orders\[Profit])
   
   ---
3. SLA Colour = IF( \[Average Resolution Hours]> AVERAGE(Fact\_Orders\[SLA\_Hours]), "#C62828", "#2E7D32")
   
   ---
4. ###### SLA Breach % =

###### &nbsp;	DIVIDE(

###### &nbsp;   		COUNTROWS(

###### &nbsp;       		FILTER(

###### &nbsp;           			Fact\_Orders,

###### &nbsp;           			Fact\_Orders\[Resolution Hours] > Fact\_Orders\[SLA\_Hours]

###### &nbsp;				)

###### &nbsp;   			),

###### &nbsp;   			COUNTROWS(Fact\_Orders)

###### &nbsp;		)

###### 

###### 5\. Profit Margin % = DIVIDE(\[Total Profit],\[Total Sales])

###### 

###### 6\. City Rank = 

###### &nbsp;	RANKX(

###### &nbsp;   		ALL(Fact\_Orders\[City]),

###### &nbsp;   			\[Total Sales],

###### &nbsp;  		 ,

###### &nbsp;   		DESC,

###### &nbsp;   		DENSE

###### &nbsp;		)

###### 

###### 7\. Average Resolution Hours = AVERAGE(Fact\_Orders\[Resolution Hours])

