## Decision 1
-Decision:The browser shouldnt be responsible for preventing double bookings.
-Reason: The reason is the browser can easily have its code hacked or reditted. So the backend API and database must be the authority.

## Decision 2
Decision:The frontend shouldnt be the final authority on whether a booking exists
Reason: Its cause the frontend can easily be reditted from the browser and the database has records of the bookings that have been made.

## Decision 3
Decision:One account can be allowed to receive and make bookings
Reason: This prevents data duplication and user having to create multiple accounts

## Decision 4
Decision:Payments whether failed or pending are all being stored in the database.
Reason: So there wont be loss of information on previous payments and incase for example a custoemrs credit card declines they can always come back nd finish up the payment