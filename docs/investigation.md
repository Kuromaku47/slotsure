# SlotSure Booking Conflict Investigation

## Incident
Two customers were successfully booked with the same staff member for the same time slot.

## Observed Behavior
Two customers received successful bookings for the same staff member and overlapping time slot.

## Reproduction Attempt
Attempt to send two booking requests for the same staff member and overlapping time slot at nearly the same time. Observe whether both requests are accepted.

## Hypothesis
The booking process may check whether a slot is available and then create the booking in separate operations. If two requests execute this sequence concurrently, both may see the slot as available before either booking is created.

## Evidence Needed
- The booking availability-check logic
- The booking creation logic
- The order in which those operations execute
- Database transaction/constraint configuration
- Logs or test results from simultaneous booking requests

## Possible Root Cause
The availability check and booking creation may not be protected as one consistent database operation, allowing concurrent requests to both pass the availability check.

## Verification
Send concurrent booking requests for the same staff member and overlapping time slot. Verify that only one booking succeeds and the other request is rejected safely.