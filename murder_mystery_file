-- confirm if the crime took place
-- SELECT * FROM crime_scene_report;

SELECT city, date, type FROM crime_scene_report WHERE type = 'murder' AND DATE = 20180115 AND city = 'SQL City'; -- yes the crime took placecrime_scene_report

-- check the description to know what to do nextcrime_scene_report
SELECT description FROM crime_scene_report WHERE type = 'murder' AND DATE = 20180115 AND city = 'SQL City';

SELECT * FROM person;
-- To check if witnesses were interviewed.
SELECT id, name, address_street_name, transcript FROM person p INNER JOIN interview i ON p.id = i.person_id WHERE address_street_name = "Franklin Ave" AND name LIKE 'Annabel%';
-- Feedback from the other witness
SELECT name, address_street_name, address_number, transcript FROM person p INNER JOIN interview i ON p.id = i.person_id WHERE address_street_name = 'Northwestern Dr' Order by address_number DESC;
-- Follow up on Annabel's interview details.
SELECT * FROM get_fit_now_check_in WHERE check_in_date = 20180109; -- From Annabel's interview
SELECT p.name, check_in_date, person_id, plate_number, membership_status FROM get_fit_now_member gf INNER JOIN person p ON gf.person_id = p.id INNER JOIN drivers_license d ON d.id = p.license_id 
INNER JOIN get_fit_now_check_in ge ON ge.membership_id= gf.id WHERE check_in_date = 20180109 AND membership_status = 'gold' AND gf.id LIKE '%48Z%';
-- From Morty's interview
SELECT * FROM get_fit_now_member WHERE id LIKE '%48Z%' AND membership_status = 'gold' ORDER BY membership_status;
SELECT * FROM drivers_license WHERE plate_number LIKE "%H42W%";
SELECT p.name, person_id, plate_number, membership_status FROM get_fit_now_member gf INNER JOIN person p ON gf.person_id = p.id INNER JOIN drivers_license d ON d.id = p.license_id WHERE gf.id LIKE '%48Z%' AND gf.membership_status = 'gold';

-- Since both witnesses were traced down to Jeremy.crime_scene_report
-- Check to see if the murderer has been caught and check descriptioncrime_scene_report
SELECT * FROM interview WHERE person_id = 67318;
-- I was hired by a woman with a lot of money. I don't know her name but I know she's around 5'5" (65") or 5'7" (67"). 
-- She has red hair and she drives a Tesla Model S. I know that she attended the SQL Symphony Concert 3 times in December 2017.
SELECT * FROM drivers_license WHERE gender = 'female' AND hair_color = 'red' AND car_make = 'Tesla' AND height = 65;
-- get the name of the woman, using facebook and date
SELECT name, person_id, event_name, date, height, hair_color, gender, car_make FROM person p INNER JOIN drivers_license d ON p.license_id = d.id INNER JOIN facebook_event_checkin f ON f.person_id = p.id WHERE gender = 'female' AND hair_color = 'red' AND car_make = 'Tesla';
-- Trying to check if she has been caught
SELECT transcript FROM interview WHERE person_id = 99716;
-- since it did not come up, she most likely has not been caught.crime_scene_report
-- Check out all income 
SELECT * FROM income ORDER BY annual_income DESC;
-- To find out the annual income of Miranda
SELECT * FROM income i INNER JOIN person p ON i.ssn = p.ssn WHERE id = 99716;
