# airbnb-clone-project
## Entity Relationship Diagram
This ERD represents the database design for the Airbnb clone project.  
It defines how users, properties, bookings, payments, reviews, and messages relate to each other.

### 🖼️ View Diagram
You can view the diagram directly on [dbdiagram.io](https://dbdiagram.io/d/Airbnb-ER-diagram-68ffad89357668b732d88d8c).

---

## 🧩 Entities and Attributes

### 1. User
- user_id (PK)
- first_name
- last_name
- email (unique)
- password_hash
- phone_number
- role (guest, host, admin)
- created_at

### 2. Property
- property_id (PK)
- host_id (FK → User.user_id)
- name
- description
- location
- pricepernight
- created_at
- updated_at

### 3. Booking
- booking_id (PK)
- property_id (FK → Property.property_id)
- user_id (FK → User.user_id)
- start_date
- end_date
- total_price
- status (pending, confirmed, canceled)
- created_at

### 4. Payment
- payment_id (PK)
- booking_id (FK → Booking.booking_id)
- amount
- payment_date
- payment_method (credit_card, paypal, stripe)

### 5. Review
- review_id (PK)
- property_id (FK → Property.property_id)
- user_id (FK → User.user_id)
- rating (1–5)
- comment
- created_at

### 6. Message
- message_id (PK)
- sender_id (FK → User.user_id)
- recipient_id (FK → User.user_id)
- message_body
- sent_at

---

## 🔗 Relationships Summary

| Relationship | Description | Type |
|---------------|--------------|------|
| User → Property | A host can have many properties | 1 → M |
| User → Booking | A guest can make many bookings | 1 → M |
| Property → Booking | A property can have many bookings | 1 → M |
| Booking → Payment | Each booking has one payment | 1 → 1 |
| Property → Review | A property can have many reviews | 1 → M |
| User → Review | A user can write many reviews | 1 → M |
| User (sender) → Message | A user can send many messages | 1 → M |
| User (recipient) → Message | A user can receive many messages | 1 → M |

---

## 🧠 Tools Used
- **dbdiagram.io** for ERD creation  
- **Markdown (requirements.md)** for documentation  
- **GitHub** for version control
## Team Roles
## Technology Stack
## Database Design
## Feature Breakdown
## API Security
## CI/CD Pipeline
