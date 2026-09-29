# SlotSure ERD

## Entities:
- User
- Business
- BusinessMember
- Service
- StaffService
- Availability
- Booking
- Payment

## Relationships:
- Business 1 ──── * BusinessMember
- User 1 ──── * BusinessMember
- Business 1 ──── * Service
- BusinessMember 1 ──── 0..1 StaffProfile
- Service 1 ──── * StaffService
- StaffProfile 1 ──── * StaffService
- StaffProfile 1 ──── * Availability
- Customer/User 1 ──── * Booking
- StaffProfile 1 ──── * Booking
- Service 1 ──── * Booking
- Business 1 ──── * Booking
- Booking 1 ──── * Payment

erDiagram
    USER ||--o{ BUSINESS_MEMBER : belongs_to
    BUSINESS ||--o{ BUSINESS_MEMBER : employs
    BUSINESS ||--o{ SERVICE : offers
    BUSINESS_MEMBER ||--o| STAFF_PROFILE : has
    SERVICE ||--o{ STAFF_SERVICE : includes
    STAFF_PROFILE ||--o{ STAFF_SERVICE : performs
    STAFF_PROFILE ||--o{ AVAILABILITY : has
    USER ||--o{ BOOKING : makes
    STAFF_PROFILE ||--o{ BOOKING : handles
    SERVICE ||--o{ BOOKING : includes
    BUSINESS ||--o{ BOOKING : receives
    BOOKING ||--o{ PAYMENT : has