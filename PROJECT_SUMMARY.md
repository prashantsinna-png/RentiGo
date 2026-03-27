RentiGo — Vehicle Rental Platform
Internship Project Report
Frontend Development Intern | Unified Mentor Pvt. Ltd.
Duration: 25/01/2026 – 25/03/2026
Prashant Singh | UMID: UMID23012678746
pptx link: Here is the Project Report Link:👇👇👇👇
https://docs.google.com/presentation/d/17y93K5nfUOmCAURNgBiny19lqQ1CUtPp/edit?usp=drivesdk&ouid=113240529899360799819&rtpof=true&sd=true 


1. Project Profile
FieldDetailsProject TitleRentiGo — Vehicle Rental PlatformProject TypeWeb-Based Application (Frontend Only)DomainE-Commerce / Transportation TechnologyTechnologiesHTML5, CSS3, JavaScript (Vanilla)Data StorageBrowser LocalStorage (Client-Side)PlatformWeb Browser — Fully Responsive DesignTarget UsersVehicle Owners, Customers, AdminCities CoveredAhmedabad, Mumbai, Delhi, BangaloreAcademic Year2025 – 2026Submitted ToUnified Mentor Pvt. Ltd., Gurugram

2. Introduction — What is RentiGo?
RentiGo is a web-based vehicle rental platform built for the Indian market. It brings vehicle owners and renters together on one simple, easy-to-use website. The whole system runs on HTML5, CSS3, and plain JavaScript — no backend server needed. Whether you want a bike for a day or a car for a month, RentiGo lets you find, compare, and book it in just a few minutes.
Verified Fleet — Every vehicle is reviewed and approved by an admin before going live.
Instant Booking — Pick your dates and confirm a booking in under 2 minutes — no phone calls.
Flexible Pricing — Choose daily, weekly, or monthly plans. Longer rentals get automatic discounts.
Always Available — The platform is online 24/7 — browse and book from any phone or computer.

3. Problem Statement
01. No Single Platform — Renters have to call multiple agencies or visit them in person just to check availability. There's no one place to search and compare.
02. Booking Is Error-Prone — Most bookings happen over phone or WhatsApp — which leads to double-bookings, confusion, and zero confirmation trail.
03. Prices Are Not Clear — Different owners charge different rates. Weekly and monthly discounts aren't communicated upfront, making it hard to plan a budget.
04. No Vehicle Verification — There's no way to know if a vehicle is insured, roadworthy, or even available. Safety and trust are serious concerns.
05. No Reviews or Ratings — New renters have no way to judge an owner's reliability. Without reviews, every booking feels like a gamble.
06. Owners Have No Insights — Vehicle owners can't track bookings, monitor revenue, or understand how well their fleet is doing — it's all guesswork.

4. Objectives, Scope & Technology
OBJECTIVES

Build a multi-role platform for Admins, Owners, and Customers
Let users browse and filter vehicles by type, city, fuel, and price
Offer live booking with automatic pricing (daily / weekly / monthly)
Give admins control over vehicle approvals and user management
Provide analytics dashboards for revenue and booking data
Include a post-rental review and rating system

SCOPE

4 cities: Ahmedabad, Mumbai, Delhi, Bangalore
2-Wheelers & 4-Wheelers
Petrol, Diesel, Electric & CNG
3 user roles: Admin / Owner / Customer
Daily / Weekly / Monthly bookings

TECH STACK

HTML5 — Page structure & markup
CSS3 — Styling & animations
JavaScript — Logic & interactivity
LocalStorage — Client-side data storage
Font Awesome — Icons & UI visuals
Google Fonts — Syne & Plus Jakarta Sans


5. Existing System — What's Broken Today
Phone-Only Booking

Customer calls an agency to check availability
Confirmation is verbal — no paper trail
Double-bookings happen all the time

Manual Record-Keeping

Everything is logged in notebooks or Excel
No booking history or search functionality
Calculations are done manually — errors are common

No Vehicle Discovery

You can't browse a fleet online
No photos, specs, or price comparisons
You have to visit the agency physically

No Reviews or Ratings

No way to check if an owner is trustworthy
First-time renters have no accountability for bad experiences

No Analytics for Owners

Owners can't see revenue or booking trends
Fleet utilisation is unknown
Decision-making is based on gut, not data

No Verification System

Vehicles aren't checked before listing
No document validation happens
Only quality, legitimate vehicles make it live
Safety and trust are major concerns


6. New System — How RentiGo Fixes All of This
Online Vehicle Marketplace

Browse 500+ verified vehicles instantly
Filter by type, city, fuel type, price range
Add favourites and compare easily

Smart Booking System

Pick dates on a calendar — price is calculated live
Daily, weekly, monthly options available
Booking stays pending until owner approval — free of charge

Three-Role Architecture

Admin controls the whole platform
Owners manage their fleet and bookings
Customers can browse, book, and leave reviews

Admin Vehicle Verification

Every vehicle needs admin approval before listing
Owners get notified when approved or rejected

Analytics Dashboard

Monthly revenue shown in bar charts
Booking stats broken down by status
Top performing vehicles ranked by earnings

Review & Rating System

5-star ratings after every completed trip
Written reviews visible on vehicle pages
Builds trust and accountability in the community


7. System Architecture — How It's All Connected
Vehicle Owner can:

Add & manage vehicles
Vehicle CRUD
Approve or reject bookings
Track fleet revenue & stats

Admin can:

Platform overview & KPIs
User management (CRUD)
All bookings management

Customer can:

Browse & search vehicles
Filter by type / city / fuel
Book with date selection
Rate & review after trip

RentiGo Core Engine — Browser LocalStorage Database:

Authentication
Vehicle CRUD
Booking Engine
Toast Notifications
Analytics Engine
Review System
Seed Data | CRUD Operations | Decision Management


8. How RentiGo Works — Step by Step
STEP 01 — Create Your Account

Fill in name, email, phone & password
Choose role: Vehicle Owner or Customer
Demo accounts available for quick testing

STEP 02 — Browse & Filter Vehicles

Search by vehicle name or keyword
Filter by city, type, fuel and price range
Sort by price, newest or name A–Z
View full specs, photos, and live availability

STEP 03 — Book Instantly

Open a vehicle page and select dates
Price is auto-calculated live
Add a note to the owner if needed
Confirm — booking status becomes Pending

STEP 04 — Hit the Road!

Owner approves — status becomes Active
Get an app notification when approved
Status becomes Completed
Rate and review your experience anytime


9. Literature Survey
[1] Web-Based Vehicle Rental System Study (Sharma et al., 2022)
Proposed a multi-role rental app using PHP/MySQL. Highlighted the need for real-time availability and online payments. RentiGo improves on availability via LocalStorage and auto-pricing.
[2] Role-Based Access Control in Web Apps (Kumar & Patel, 2021)
Explored RBAC models for e-commerce. Concluded that clearly separating Admin, Owner, and Customer roles reduces risks and improves user experience — which is exactly what RentiGo does.
[3] Client-Side Data with LocalStorage (MDN Web Docs, 2023)
Documented LocalStorage as a practical solution for lightweight prototype apps that don't require a server. RentiGo uses it for all CRUD operations, seeded with realistic dummy data.
[4] Platform Analysis — OLA, Rapido, Zoomcar (Industry Research, 2024)
Existing platforms focus on narrow niches like self-drive or bike taxis. RentiGo unifies both 2-Wheeler and 4-Wheeler owner-to-customer rentals in one interface.
[5] Responsive Web Design Best Practices (Google, 2023)
Stresses mobile-first design. RentiGo uses CSS Grid, Flexbox, and media queries to support screens from 320px to 1920px — fully functional on any device.

10. Data Collection — What Data RentiGo Stores
1. Users Entity
FieldDescriptionFieldDescriptionidUnique user ID (e.g., u1, u2)statusactive / inactivenameFull namephone10-digit mobile numberemailLogin email (unique)joinedAccount creation datepasswordPlain text (prototype)agency / cityOwner's agency name & cityroleadmin / owner / customer
2. Vehicles & Bookings Entities
(id, ownerId, name, brand, model, year, type, fuel, prices, city, status, booking dates, duration, total cost, notes)
3. Vehicles store: icon, colour, description, approval flag, availability status, seating capacity, transmission type, and 3 price tiers (daily / weekly / monthly)
4. Bookings store: vehicle ID, customer ID, owner ID, pickup date, return date, number of days, total price, status (pending / active / completed / cancelled), and an optional customer note

11. Data Sources & Collection Method
1. Initialization — Seed / Dummy Data
The app pre-loads with 6 users, 10 vehicles, and sample bookings on first launch. Data is stored as JSON under keys like 'rentigo_users' and 'rentigo_vehicles'.
2. Read Operation — User Registration
New users fill a form. Data is validated and saved to LocalStorage. All reads use JSON.parse() with an empty-array fallback if the key doesn't exist yet.
3. Write / Update — Owner Fleet Addition
Owners add vehicles through a modal form with 12 fields. After any change, the whole updated array is re-saved using JSON.stringify() — last write wins.
4. Session Management — Booking Form Input
Customers pick dates on the vehicle page. Price is auto-calculated. Login state is kept in sessionStorage so users stay logged in on page refresh.
5. Data Validation — Review Submission
After a trip, customers rate and review. Forms validate email format (regex), phone length (10 digits), and required fields before any save is allowed.

12. EDA & Data Pre-Processing
EDA — Seed Dataset Insights (10 Vehicles)

50% 2-Wheeler (5 vehicles) / 50% 4-Wheeler (5 vehicles)
50% Ahmedabad (5 vehicles) / 50% Mumbai (5 vehicles)
90% Approved (9 vehicles) / 10% Pending (1 vehicle)

Price Range Analysis:

Budget ₹250 – ₹800: Activa, Jupiter, Shine, RE Classic
Mid-Range ₹1,200 – ₹2,000: Swift Dzire, Honda City ZX
Premium ₹2,500 – ₹3,500: Creta, Nexon EV, Innova, Pulsar

Data Pre-Processing & Cleaning:
Input Validation — All forms check email format with a regex pattern. Phone numbers must be 10 digits starting with 6–9. Required fields are blocked from saving if empty.
Duplicate Detection — On signup, the system checks if an email already exists. If it does, the save is stopped and an error is shown to the user.
Auto-Pricing — If an owner skips weekly or monthly pricing, the system fills it in: Weekly = Daily × 6.5, Monthly = Daily × 25.
Date Normalisation — All dates are stored as ISO strings (YYYY-MM-DD). Booking duration uses Math.max(1, ...) to guarantee at least 1 rental day.
HTML Sanitisation — User text is passed through escapeHtml() before display, replacing <, >, and & with safe HTML entities to block XSS attacks.
Status State Machine — Booking states follow a strict flow: Pending → Active → Completed or Cancelled. Invalid transitions are blocked by the system.

13. Methodology — How We Built RentiGo
Development Phases:

Planning — Gathered requirements, defined user roles, listed all features
Design — Created UI wireframes, designed data schema, chose colour theme
Development — Built HTML5 structure, applied CSS3 styling, wrote all JS logic
Testing — Functional testing, role-based access check, cross-browser testing
Evaluation — Reviewed all outputs, fixed remaining bugs, performance check

Analytical Techniques & Justification:
TechniqueUsed ForJustificationRBAC (Role-Based Access)Navigation & dashboardsEach user sees only their relevant pages — no unauthorised accessState Machine (Bookings)Booking lifecyclePrevents invalid status jumps (e.g. going from Pending directly to Completed)Regex ValidationLogin & registration formsLightweight email and phone validation without any third-party libraryAuto-Pricing AlgorithmVehicle listing & bookingWeekly = Daily × 6.5Observer / Toast SystemReal-time notificationsEvent-driven alerts show success/error messages without page reloadsCSS Grid + FlexboxAll UI layoutsGrid for columns, Flexbox for alignment — no CSS framework required

14. Output Screens & Key Features
Home / Landing Page

Hero banner with call-to-action buttons
Platform stats: 500+ vehicles, 10K+ renters
Featured vehicle carousel
'Why RentiGo?' feature highlights
'How It Works' 4-step guide
Responsive footer with city links

Login & Register Page

Tabbed interface: Login / Register
Role selector — Customer or Owner
Password strength indicator bar
Demo account quick-fill buttons
Form validation with live error messages
Session-based auto-login on reload

Browse Vehicles Page

Keyword search bar
Filters: type, city, fuel, price range
Sort by price, newest, or name A–Z
Vehicle cards with status badges
Favourite/heart toggle on every card
Price displayed per day on each card

Admin Dashboard

KPI stat cards for quick overview
Monthly revenue bar chart
Booking breakdown by status
Top vehicles by revenue table
Vehicle approval queue
Full user management (add/edit/delete)

Owner Fleet Management

List of all owned vehicles with status
Add Vehicle modal with 12 input fields
Approve or reject booking requests
Fleet revenue statistics
Vehicle status toggle (available/rented)
Booking history at a glance

Customer Booking Panel

Tabbed view: All / Pending / Active / Done
Booking card with date grid
Live price breakdown panel
Cancel booking before owner approves
Post-trip review submission modal
Favourites saved list


15. Future Scope — Where RentiGo Goes Next
Phase 2 — Backend Integration

Move to Node.js + Express.js REST API
MongoDB or MySQL for real data storage
JWT authentication + encrypted passwords
Cloud deployment (AWS / Render / Railway)

Phase 3 — Mobile Application

React Native / Flutter cross-platform app
Push notifications for booking updates
GPS-based vehicle tracking
Offline mode with data sync

Phase 4 — Expanded Marketplace

Grow from 4 cities to 100+ pan-India
Corporate & bulk rental packages
Long-term lease options (3–12 months)
Insurance provider partnerships

Online Payments

Razorpay / Stripe payment gateway
UPI, debit/credit card, net banking
Auto-refund on booking cancellation
PDF invoices for completed bookings

AI & Smart Features

ML-based vehicle price recommendations
Demand forecasting by city & vehicle type
NLP smart search: 'cheap bike near me'
Automated booking fraud detection

Advanced Analytics

Real-time analytics using WebSockets
Exportable owner earnings PDF reports
Customer loyalty & referral rewards
A/B testing dashboard for UI improvements


16. Bibliography & References
Web Documentation

[1] MDN Web Docs, "HTML5 Reference & Tutorials", Mozilla Foundation, 2024.
[2] MDN Web Docs, "CSS3 — Cascading Style Sheets", Mozilla Foundation, 2024.
[3] MDN Web Docs, "JavaScript Guide", Mozilla Foundation, 2024.
[4] MDN Web Docs, "Window.localStorage", Mozilla Foundation, 2024.

UI Libraries & Fonts

[5] Font Awesome, "Free Icons v6.5.0", Fonticons Inc., 2024. — fontawesome.com
[6] Google Fonts, "Syne & Plus Jakarta Sans", Google LLC, 2024. — fonts.google.com

Industry References

[7] Zoomcar Inc., "Zoomcar — Self-Drive Car Rentals India", 2024. — zoomcar.com
[8] Rapido, "Bike Taxi & Auto Platform", 2024. — rapido.bike
[9] OLA Mobility Inc., "OLA Rentals — Vehicle Rental Platform", 2024. — olacabs.com

Textbooks & Research Papers

[10] J. Duckett, "HTML and CSS: Design and Build Websites", Wiley, 2011. ISBN: 978-1118008188.
[11] D. Flanagan, "JavaScript: The Definitive Guide, 7th Ed.", O'Reilly, 2020. ISBN: 978-1491952023.
[12] E. Freeman & E. Robson, "Head First Design Patterns", O'Reilly, 2021. ISBN: 978-0596007126.


Submitted to Unified Mentor Pvt. Ltd., DLF Forum, Cybercity, Phase III, Gurugram, Haryana 122002
Frontend Development Intern | Jan 2026 – Mar 2026 | UMID: UMID23012678746
