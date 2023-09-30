SELECT *
FROM "DATAFEEDS"."SP_500"
WHERE company_name = 'Iron Mountain Inc' AND desktop_pages_per_visit = 3.5


SELECT company_name, ticker, desktop_visits, mobile_visits
FROM "DATAFEEDS"."SP_500"
WHERE desktop_visits = 0 OR mobile_visits = 0
ORDER BY company_name


SELECT company_name, date, desktop_visits
FROM "DATAFEEDS"."SP_500"
WHERE desktop_visits >= 200 AND desktop_visits <=300
ORDER BY desktop_visits ASC


SELECT company_name, date, desktop_bounce_rate
FROM "DATAFEEDS"."SP_500"
GROUP BY date, company_name, desktop_bounce_rate
ORDER BY date DESC


SELECT AVG (desktop_bounce_rate) AS average_desktop_bounce, AVG (mobile_bounce_rate) AS average_cell_bounce
FROM "DATAFEEDS"."SP_500"


SELECT company_name, ticker, domain, ROUND(mobile_pages_per_visit, 0) AS rounded_mobile_pages, ROUND(desktop_pages_per_visit, 0) AS rounded_desktop_pages
FROM "DATAFEEDS"."SP_500"
ORDER BY rounded_mobile_pages desc, rounded_desktop_pages


SELECT company_name, SUM (mobile_visits) AS total_mobile_visits
FROM "DATAFEEDS"."SP_500"
GROUP BY company_name
ORDER BY SUM(mobile_visits) asc


SELECT company_name, ROUND(AVG (desktop_visits), 0) AS rounded_desktop_visits
FROM "DATAFEEDS"."SP_500"
GROUP BY company_name
ORDER BY company_name asc

CTE

WITH cell_visits 
AS (SELECT * FROM "DATAFEEDS"."SP_500" WHERE mobile_visits <= 100)
SELECT company_name, ticker, mobile_visits FROM cell_visits
GROUP BY company_name, ticker, mobile_visits
ORDER BY company_name ASC
