# SlotSure Requirements

## Functional Requirements
- Customers can view available time slots for a specific staff member and service.
- Customers can create a booking for a specific time slot.
- Staff and Owners can view their upcoming bookings.
- The system must prevent double-bookings for the same staff member and time slot.
- The system must handle payment attempts and record failures/refunds.

## Non-Functional Requirements
- Consistency: The database must guarantee that concurrent booking requests do not both succeed for the same slot.
- Performance: Availability checks should respond within 2 seconds.
- Security: Authentication and authorization must protect business data.
- Reliability: The system must gracefully reject a booking if the slot was just taken.

## Rules and Constraints
- One Booking belongs to exactly one Service, one Customer, one Staff Member, and one Business.
- A Staff Member cannot have overlapping active bookings.
- A Booking can have multiple Payment attempts (one-to-many).
- A User's role (Customer, Employee, Owner) is determined by their BusinessMember link, not by separate accounts.