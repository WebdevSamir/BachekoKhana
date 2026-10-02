# BachekoKhana 🍲

**Surplus Food. Shared With Dignity.**

BachekoKhana is a food donation and redistribution platform designed and developed by **Samir Aryan**. It connects food providers with people and communities who need food through structured donations, food discovery, requests, and coordinated pickup.

## Current version

This repository contains the responsive frontend prototype for the BachekoKhana platform.

### Core flows

- Find available food near you
- Donate surplus food
- Register as a provider or food seeker
- Request available food
- Track donation/request status
- Volunteer rescue workflow
- Impact dashboard
- Food safety information

## Tech

- HTML5
- CSS3
- Vanilla JavaScript
- Responsive/mobile-first UI
- No external backend required for the prototype
The core idea should be more than a simple food-donation contact form. BachekoKhana should work as a two-sided food redistribution platform:

Food Providers → BachekoKhana → Verified Needers

A provider can list available surplus food, while a needy person can register, see available food, request it, and receive pickup/delivery information.

Recommended website structure
1. Home Page
Hero: “Don’t Waste Food. Share It.”
Find Food
Donate Food
How It Works
Available Food
Impact statistics
Provider/Needer registration
Login
Emergency food request
Contact
2. Food Provider Portal

Providers could be:

Restaurants
Hotels
Cafes
Bakeries
Event organizers
Households
Grocery stores
Schools/colleges
Organizations

Provider registration:

Name/organization
Phone/email
Address
Food type
Approximate quantity
Vegetarian/non-vegetarian
Preparation date/time
Expiry/safe-consumption time
Pickup location
Photos
Available until

Then:

Donate Food → Submit Donation → Verification → Available to Needers → Pickup/Delivery → Completed

3. Needer Portal

A person can register with:

Full name
Phone
Location
Number of people
Food preference
Required quantity
Identification/verification information where appropriate

After login:

Available Food → View Details → Request Food → Approval/Reservation → Pickup/Delivery → Completed

Don't make the system automatically assume that anyone who registers is genuinely in need. You'd want a verification/moderation layer to reduce abuse and duplicate claims.

4. Food Listing Page

Each donation could appear as a card:

🍱 20 Meal Boxes Available
📍 Kathmandu
🥗 Vegetarian
⏰ Available until 7:00 PM
👥 Serves approximately 20 people
Request Food

Filters:

Location
Food type
Vegetarian/non-vegetarian
Quantity
Available now
Pickup/delivery
5. Admin Dashboard

This is essential.

Admin should be able to manage:

Providers
Needers
Food donations
Food requests
Verification
Reports
Suspicious accounts
Expired food
Pickup status
Delivery status
Statistics

Dashboard example:

BACHEKOKHANA ADMIN
──────────────────────────────
Total Providers       248
Verified Needers      1,426
Active Donations       87
Meals Available      2,340
Meals Distributed    18,920
Pending Requests        42
Expired Donations       11
──────────────────────────────
Recent Donations
Recent Requests
Pending Verifications
6. Matching System

This is where the project becomes substantially more useful.

Suppose a restaurant in Baneshwor has:

50 meal boxes available until 8 PM.

The system can identify registered needers near Baneshwor and notify them.

Provider
→ 50 meals available

BachekoKhana
→ Finds nearby eligible needers

Needer
→ Receives notification

Needer
→ Requests 5 meals

Provider/Admin
→ Confirms

System
→ Marks 5 meals reserved

This prevents the website from becoming just a directory of phone numbers.

7. Food Safety

You should include this from the beginning.

Every donation should capture:

Preparation time
Food type
Storage condition
Safe consumption deadline
Allergens where known
Provider declaration

And prominently display:

Food Safety Notice: Providers are responsible for accurately reporting food preparation, storage, and safety information. BachekoKhana should not represent food as safe solely because it has been listed.

You should also establish actual food-safety rules with local authorities/qualified professionals before launching publicly.

Suggested technology

For a serious student/research/project version:

Frontend

React / Next.js
Tailwind CSS
Responsive mobile-first design

Backend

Node.js + Express/NestJS
or
Laravel/PHP if you want to build it with your existing PHP knowledge

Database

PostgreSQL

Authentication

Email/password
Phone OTP
Role-based authentication

Roles

ADMIN
  ↓
PROVIDER
  ↓
NEEDER
  ↓
VOLUNTEER / DELIVERY PARTNER

Useful integrations

Google Maps/OpenStreetMap
SMS/OTP
Email notifications
WhatsApp/contact integration
Push notifications
QR-based pickup verification
The main database model

A clean initial architecture could be:

Users
 ├── Providers
 ├── Needers
 └── Admins

Providers
 └── Donations
       └── Food Items

Needers
 └── Food Requests

Donations
 └── Requests

Requests
 └── Pickup / Delivery

Users
 └── Notifications

For example:

DONATION
────────────────────
id
provider_id
food_name
description
quantity
unit
food_type
prepared_at
available_until
pickup_address
latitude
longitude
status
created_at

And:

FOOD_REQUEST
────────────────────
id
donation_id
needer_id
requested_quantity
status
pickup_time
created_at
Pages I would build
/
├── Home
├── About
├── How It Works
├── Available Food
├── Donate Food
├── Request Food
├── Food Details
├── Contact
│
├── /auth
│   ├── login
│   ├── register
│   └── forgot-password
│
├── /provider
│   ├── dashboard
│   ├── donations
│   ├── create-donation
│   ├── requests
│   └── profile
│
├── /needer
│   ├── dashboard
│   ├── available-food
│   ├── my-requests
│   └── profile
│
└── /admin
    ├── dashboard
    ├── providers
    ├── needers
    ├── donations
    ├── requests
    ├── verification
    ├── reports
    └── settings
The homepage could have this positioning

BachekoKhana

Turn Surplus Food Into Someone’s Next Meal.

Donate surplus food. Find available meals. Reduce food waste.

Donate Food | Find Food

Then show:

How BachekoKhana Works

1. Providers List Food → 2. We Match → 3. Needers Request → 4. Food Reaches People

And an impact section:

18,920+ Meals Shared
248 Food Providers
1,426 Registered Needers
2,340 kg Food Saved

Those numbers should be dynamic database values, not hardcoded marketing numbers.

One important change I'd make

Don't build “provider contacts needy person directly” as the primary workflow.

Instead:

Provider → Donation Listing → Platform Verification → Needer Request → Matching → Confirmation → Pickup/Delivery

That gives you control over quantity, timing, verification, duplicate requests, expired food, and abuse, and it makes BachekoKhana an actual platform rather than a food-donation noticeboard.

If you're building this as one of your serious portfolio projects, I would make BachekoKhana a full-stack web application with three dashboards (Admin, Provider, Needer), real-time donation/request status, location-based matching, and a proper database, rather than just a visually attractive frontend.

## Project author

**Samir Aryan**

Designed & Developed by Samir Aryan.

## Disclaimer

This prototype is for demonstration and development purposes. A production deployment should add authentication, database persistence, provider/needer verification, moderation, food-safety compliance, notifications, and secure location handling.
