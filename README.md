# goit-rdb-hw-05
1)
 SELECT 
	order_details.*,
	(SELECT customer_id 
	FROM orders 
    WHERE order_details.order_id = orders.id) AS customer_id
FROM order_details;

2)
SELECT *
FROM order_details
WHERE order_id IN (
	SELECT order_id
    	FROM orders
    	WHERE shipper_id = 3);
  
3)
SELECT 
	order_id, 
    	AVG(quantity) AS avg_q
FROM (
	SELECT *
    	FROM order_details
   	WHERE quantity > 10
    ) AS t
GROUP BY order_id;
