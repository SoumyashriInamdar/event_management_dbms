 Organizer Table
INSERT INTO Organizer (OrganizerID, OrganizerName, ContactEmail, ContactPhone) VALUES
(1, 'Amit Kumar', 'amit.kumar@example.com', '9876543210'),
(2, 'Sonia Singh', 'sonia.singh@example.com', '9876543211'),
(3, 'Rahul Verma', 'rahul.verma@example.com', '9876543212'),
(4, 'Priya Desai', 'priya.desai@example.com', '9876543213'),
(5, 'Vikrant Mehta', 'vikrant.mehta@example.com', '9876543214');


 Event Table
INSERT INTO Event (EventID, EventName, EventDate, Location, Description, OrganizerID) VALUES
(1, 'Tech Fest', '2024-08-01', 'Main Auditorium', 'A technical festival', 1),
(2, 'Cultural Fest', '2024-08-02', 'Open Ground', 'A cultural festival', 2),
(3, 'Sports Day', '2024-08-03', 'Sports Complex', 'A day full of sports activities', 3),
(4, 'Music Concert', '2024-08-04', 'Main Auditorium', 'A musical night', 4),
(5, 'Art Exhibition', '2024-08-05', 'Art Gallery', 'An exhibition of artworks', 5);


 Attendee Table
INSERT INTO Attendee (AttendeeID, AttendeeName, Email, PhoneNumber) VALUES
(1, 'Rohan Sharma', 'rohan.sharma@example.com', '9876543215'),
(2, 'Neha Gupta', 'neha.gupta@example.com', '9876543216'),
(3, 'Vikram Singh', 'vikram.singh@example.com', '9876543217'),
(4, 'Kavita Joshi', 'kavita.joshi@example.com', '9876543218'),
(5, 'Arjun Rao', 'arjun.rao@example.com', '9876543219');


 Pass Table
INSERT INTO Pass (PassID, EventID, AttendeeID, PurchaseDate, TicketType, Price) VALUES
(1, 1, 1, '2024-07-10', 'Regular', 500.00),
(2, 1, 2, '2024-07-11', 'Regular', 300.00),
(3, 2, 3, '2024-07-12', 'Regular', 400.00),
(4, 3, 4, '2024-07-13', 'Regular', 200.00),
(5, 4, 5, '2024-07-14', 'Regular', 600.00);


 Venue Table
INSERT INTO Venue (VenueID, VenueName, Location, Capacity) VALUES
(1, 'Main Auditorium', 'Central Campus', 500),
(2, 'Open Ground', 'North Campus', 1000),
(3, 'Sports Complex', 'South Campus', 300),
(4, 'Art Gallery', 'West Campus', 200),
(5, 'Conference Hall', 'East Campus', 150);


 Event_head Table
INSERT INTO Event_head (EheadID, EheadName, Phone) VALUES
(1, 'Manish Patel', '9876543220'),
(2, 'Priya Nair', '9876543221'),
(3, 'Kiran Joshi', '9876543222'),
(4, 'Deepak Chawla', '9876543223'),
(5, 'Meera Nambiar', '9876543224');


Session Table
INSERT INTO Session (SessionID, EventID, SessionName, StartTime, EndTime, EheadID) VALUES
(1, 1, 'Opening Ceremony', '09:00:00', '10:00:00', 1),
(2, 1, 'Keynote Speech', '10:00:00', '11:00:00', 2),
(3, 2, 'Dance Performance', '11:00:00', '12:00:00', 3),
(4, 3, 'Football Match', '14:00:00', '16:00:00', 1),
(5, 4, 'Live Concert', '19:00:00', '21:00:00', 4);
