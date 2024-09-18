
create table queries:


CREATE TABLE Organizer (
    OrganizerID INT PRIMARY KEY,
    OrganizerName VARCHAR(100),
    ContactEmail VARCHAR(100),
    ContactPhone VARCHAR(15)
);


CREATE TABLE Event (
    EventID INT PRIMARY KEY,
    EventName VARCHAR(100),
    EventDate DATE,
    Location VARCHAR(100),
    Description TEXT,
    OrganizerID INT,
    FOREIGN KEY (OrganizerID) REFERENCES Organizer(OrganizerID) ON DELETE CASCADE ON UPDATE CASCADE
);


CREATE TABLE Attendee (
    AttendeeID INT PRIMARY KEY,
    AttendeeName VARCHAR(100),
    Email VARCHAR(100),
    PhoneNumber VARCHAR(15)
);


CREATE TABLE Pass (
    PassID INT PRIMARY KEY,
    EventID INT,
    AttendeeID INT,
    PurchaseDate DATE,
    TicketType VARCHAR(50),
    Price DECIMAL(10, 2),
    FOREIGN KEY (EventID) REFERENCES Event(EventID) ON DELETE CASCADE ON UPDATE CASCADE,
    FOREIGN KEY (AttendeeID) REFERENCES Attendee(AttendeeID) ON DELETE CASCADE ON UPDATE CASCADE
);


CREATE TABLE Venue (
    VenueID INT PRIMARY KEY,
    VenueName VARCHAR(100),
    Location VARCHAR(100),
    Capacity INT
);


CREATE TABLE Event_head (
    EheadID INT PRIMARY KEY,
    EheadName VARCHAR(100),
    Phone VARCHAR(15)
);


CREATE TABLE Session (
    SessionID INT PRIMARY KEY,
    EventID INT,
    SessionName VARCHAR(100),
    StartTime TIME,
    EndTime TIME,
    EheadID INT,
    FOREIGN KEY (EventID) REFERENCES Event(EventID) ON DELETE CASCADE ON UPDATE CASCADE,
    FOREIGN KEY (EheadID) REFERENCES Event_head(EheadID) ON DELETE CASCADE ON UPDATE CASCADE
);
