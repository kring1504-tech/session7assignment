-- Create the Orders table
CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    user_name VARCHAR(50),
    total_amount DECIMAL(10, 2),
    order_date DATE
);

-- Insert 5 sample rows (including one NULL total_amount)
INSERT INTO Orders (order_id, user_name, total_amount, order_date) VALUES
(1, 'Aarav', 1250.50, '2026-10-01'),
(2, 'Priya', 3400.00, '2026-10-02'),
(3, 'Aarav', 899.00, '2026-10-05'),
(4, 'Rohan', NULL, '2026-10-10'),
(5, 'Priya', 450.75, '2026-10-12');

SELECT 
    user_name, 
    COUNT(*) AS order_count
FROM Orders
GROUP BY user_name;

SELECT 
    AVG(total_amount) AS average_total_amount
FROM Orders;

SELECT 
    SUM(total_amount) AS total_sales
FROM Orders
WHERE total_amount IS NOT NULL;




