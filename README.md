# goit-rdb-hw-05
1)
 SELECT 
	order_details.*,
	(SELECT customer_id 
	FROM orders 
    WHERE order_details.order_id = orders.id) AS customer_id
FROM order_details;

2)
