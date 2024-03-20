-- Simple starting query

SELECT appt_id, date, mileage, appt_type
FROM all_appts_2023
;

-- What was my total mileage driven for 2023?

SELECT ROUND(SUM(mileage), 2)
FROM all_appts_2023
;

-- Of my 694 total field appointments, how many of each type did I complete?

SELECT appt_type, COUNT(appt_id) AS appt_count
FROM all_appts_2023
GROUP BY appt_type
;

-- What were the total, average, longest, and shortest mileage per appointment type?

SELECT 
	appt_type, 
	COUNT(appt_id) AS appt_count, 
    ROUND(SUM(mileage), 2) AS total_mileage,
	ROUND(AVG(mileage), 2) AS avg_milage,
    MAX(mileage),
    MIN(mileage)
FROM all_appts_2023
GROUP BY appt_type
ORDER BY appt_count DESC
;

-- It appears that the overwhelming majority of appointments were tours.
-- But exactly what percentage of all appointments did the tours make up?

SELECT 
	ROUND(((
    (
    SELECT
		COUNT(appt_id)
	FROM all_appts_2023
    WHERE appt_type = 'Tour'
    )
	/COUNT(appt_id)) *100), 2) AS tour_percentage
FROM all_appts_2023
;

-- How many appointments was I assigned per day?

SELECT 
	date, 
	COUNT(appt_id) AS appt_count 
FROM all_appts_2023
GROUP BY date
ORDER BY date
;

-- How many days of the year did I work?

SELECT COUNT(DISTINCT date)
FROM all_appts_2023
;

 -- How many clients did I work with?

SELECT COUNT(DISTINCT client)
FROM all_appts_2023
;

-- And how often did I work with each of those 395 clients?

SELECT client, count(appt_id) AS appt_count
FROM all_appts_2023
GROUP BY client
ORDER BY appt_count DESC
;

