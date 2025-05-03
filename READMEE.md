Multi_Step_User_Profile_Update_Form

This is a comprehensive full-stack task involving dynamic frontend behavior, real-time validation, and backend integration.

To approach this efficiently:

Tech Stack Used

Frontend: React.js (with basic hooks and state management, no third-party UI libs)
Backend: Node.js + Express
Database: MongoDB (for storing user profiles, countries, states, cities)

Deployment:
Frontend: Vercel or Netlify (free tier)
Backend + DB: Render or Railway (MongoDB Atlas for DB)

Functional Breakdown
Frontend
Step 1: Personal Info
Profile Photo

Input: File

Validate type (JPG/PNG) + size (<= 2MB)

Show live preview

Username

4-20 chars, no spaces

On blur: Call API to check availability

Password Section

If current password entered: Show new password

New password:

8+ chars, 1 special char, 1 number

Password strength indicator

Step 2: Professional Details
Profession Dropdown

If "Entrepreneur" → Show “Company Name” field (required)

Dynamic gender field

If "Other" selected → Show custom gender textbox

Step 3: Preferences
Country Dropdown

OnChange → Reset state & city, fetch related states

State Dropdown

OnChange → Fetch related cities

Date of Birth

Use <input type="date" /> with max date as today

Subscription Plan: Radio buttons

Newsletter: Default checked

Final Step: Review Summary
Backend (Node.js + Express)
Routes

GET /countries, GET /states/:countryId, GET /cities/:stateId

POST /check-username – returns availability

POST /update-profile – saves profile

Validation

Validate fields again on server

File validation (size/type)

Password policy
