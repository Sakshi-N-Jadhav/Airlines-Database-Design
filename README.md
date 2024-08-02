# CLOUD-9 Airlines Database Design

## Introduction

This repository contains the database design for CLOUD-9 Airlines, created to streamline the flight reservation and information processes following the merger of SKY-HIGH Airlines and ALWAYS-ON-TIME Airlines. This report details the design assumptions, constraints, ER schema, and table structures required for managing passenger travel effectively.

## ER Schema Diagram

The ER schema diagram models the various entities and relationships involved in the flight reservation and information system. The key entities include:

- **Passenger**: Represents customers booking flights.
- **Reservation**: Tracks flight bookings made by passengers.
- **Flight**: Represents the scheduled flights.
- **Flight Leg**: Details specific segments of a flight.
- **Aircraft**: Represents the airplanes used for flights.
- **Airport**: Represents the airports involved in flights.
- **Seat**: Represents individual seats on an aircraft.

## Table Implementation

The ER diagram was converted into a set of relational tables with primary and foreign keys defined to maintain data integrity and relationships. The tables are as follows:

1. **Passenger Table**
   - Primary Key: `PassengerID`
   - Attributes: `Name`, `Address`, `Phone Number`, `Email`

2. **Reservation Table**
   - Primary Key: `ReservationID`
   - Foreign Keys: `PassengerID`, `FlightLegID`, `SeatID`
   - Attributes: `ReservationDate`, `Status`

3. **Flight Table**
   - Primary Key: `FlightID`
   - Attributes: `FlightNumber`, `DepartureAirport`, `ArrivalAirport`

4. **Flight Leg Table**
   - Primary Key: `FlightLegID`
   - Foreign Key: `FlightID`
   - Attributes: `LegNumber`, `DepartureTime`, `ArrivalTime`, `AircraftID`

5. **Aircraft Table**
   - Primary Key: `AircraftID`
   - Attributes: `ModelCode`, `Capacity`, `Airline`

6. **Airport Table**
   - Primary Key: `AirportID`
   - Attributes: `AirportCode`, `Name`, `Location`

7. **Seat Table**
   - Primary Key: `SeatID`
   - Foreign Key: `AircraftID`
   - Attributes: `SeatNumber`, `Class`

## Assumptions and Constraints

- **Reservation Capacity**: No flight leg may have more reservations than the aircraft can accommodate.
- **Aircraft Compatibility**: Flight legs landing or taking off from an airport can only be assigned to aircraft with a model code appropriate for the runway size of that airport.
- **Seat Reservation**: During a specific flight leg, only one active reservation may be made for any given seat on an aircraft.
- **Regulations and Fees**: Airports are subject to the state-specific regulations and fees in which they are situated.
- **Flight Leg Sequence**: Every trip's leg must be taken in a specific order.
- **Weekend Operations**: Operations during weekends are restricted to routes that generate profit.
- **Aircraft Usage**: There are limitations on the airports that each type of aircraft can use.

## Conclusion

This repository presents a detailed design for the CLOUD-9 Airlines database, incorporating the key entities, relationships, assumptions, and constraints required for a robust and efficient flight reservation and information system. The ER schema and table implementations align with corporate guidelines and specifications, ensuring data integrity and operational efficiency.



