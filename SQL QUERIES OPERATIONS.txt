SQL QUERIES OPERATIONS

 1. Retrieve All Events Organized by a Specific Organizer

SELECT EventName, EventDate, Location, Description
FROM Event
WHERE OrganizerID = 1;


2. List All Attendees for a Specific Event

SELECT Attendee.AttendeeName, Attendee.Email, Attendee.PhoneNumber
FROM Attendee
JOIN Pass ON Attendee.AttendeeID = Pass.AttendeeID
WHERE Pass.EventID = 1;


 3. Find All Sessions for a Specific Event

SELECT SessionName, StartTime, EndTime, EheadName
FROM Session
JOIN Event_head ON Session.EheadID = Event_head.EheadID
WHERE Session.EventID = 1;


 4. List All Events Held at a Specific Venue

SELECT EventName, EventDate, OrganizerName
FROM Event
JOIN Organizer ON Event.OrganizerID = Organizer.OrganizerID
WHERE Location = 'Main Auditorium';


 5. Calculate Total Revenue Generated from a Specific Event

SELECT SUM(Price) AS TotalRevenue
FROM Pass
WHERE EventID = 1;



 6. Retrieve Event Details Along with Organizer Information

SELECT EventName, EventDate, Event.Location, Event.Description, Organizer.OrganizerName, Organizer.ContactEmail, Organizer.ContactPhone
FROM Event
JOIN Organizer ON Event.OrganizerID = Organizer.OrganizerID;


 7. Find All Events Along with Their Sessions

SELECT Event.EventName, Session.SessionName, Session.StartTime, Session.EndTime
FROM Event
JOIN Session ON Event.EventID = Session.EventID
ORDER BY Event.EventName;


 8. Count the Number of Attendees for Each Event

SELECT Event.EventName, COUNT(Pass.AttendeeID) AS NumberOfAttendees
FROM Event
JOIN Pass ON Event.EventID = Pass.EventID
GROUP BY Event.EventName;


9 .Update event location for the events held at the updated venue
UPDATE Event
SET Location = 'Open Ground'
WHERE Location = 'Main Auditorium';

10. Delete all passes and their corresponding attendee information for a specific event:
 Delete passes for a specific event
DELETE FROM Pass
WHERE EventID = 1;

 Delete attendees that are no longer associated with any passes
DELETE FROM Attendee
WHERE AttendeeID NOT IN (SELECT DISTINCT AttendeeID FROM Pass);