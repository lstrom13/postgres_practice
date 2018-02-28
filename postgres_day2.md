# Postgres Practice

### Which languages are spoken in the ten largest (area) countries?

WITH

biggest_ten AS

(SELECT surfacearea, code
FROM country
ORDER BY surfacearea DESC
LIMIT 10)

SELECT cl.language, countrycode
FROM biggest_ten JOIN
countrylanguage cl ON
(cl.countrycode = biggest_ten.code)
Order BY surfacearea DESC
