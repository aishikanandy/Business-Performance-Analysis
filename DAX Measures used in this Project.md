##### **DAX Measures used in this Project:**



1. Total Sales = SUM(Fact\_Orders\[Sales])
   
   ---
2. Total Profit = SUM(Fact\_Orders\[Profit])
   
   ---
3. SLA Colour = IF( \[Average Resolution Hours]> AVERAGE(Fact\_Orders\[SLA\_Hours]), "#C62828", "#2E7D32")
   
   ---
4. SLA Breach % =

DIVIDE(

COUNTROWS(

FILTER(

Fact_Orders, Fact_Orders[Resolution Hours] > Fact_Orders[SLA_Hours]

)

),

COUNTROWS(Fact_Orders)

)

5. Profit Margin % = DIVIDE(\[Total Profit],\[Total Sales])

6. City Rank = 

RANKX(

ALL(Fact_Orders[City]),

[Total Sales],

,

DESC,

DENSE

)

7. Average Resolution Hours = AVERAGE(Fact\_Orders\[Resolution Hours])


