# MindQuilt - Build Instructions

## Project Overview
MindQuilt is a mental health platform with two layers:
1. A free blog covering mental health education
2. A premium marketplace connecting users to verified mental health experts

The platform must feel calm, safe, and professional at all times.

## Tech Stack
- Frontend: Plain HTML, CSS, JavaScript only. No frameworks.
- Auth and Database: Supabase
- Hosting: Vercel
- Booking: Cal.com embedded widgets
- Payments: Stripe payment links
- Email: Resend API

## Supabase Credentials
- Project URL: https://lxxtdlfgdcckjlbdleak.supabase.co
- Anon Public Key: sb_publishable_dLQYXfa47laAeaMV8M83_g_1FcV6rKK

## Design System
- Primary Color: #8FAF8F (Sage Green) - buttons, links, accents
- Background: #F9F7F4 (Warm Off-White) - page background
- Text Color: #2D2D2D (Dark Charcoal) - all body text
- Accent/CTA: #C4826A (Warm Clay) - call to action buttons
- Card Background: #FFFFFF (White) - blog cards, expert cards
- Heading Font: DM Serif Display
- Body Font: DM Sans
- Line Height: 1.7
- Border Radius: 12px
- Max Content Width: 1100px
- Mobile-first. Every page must work perfectly on phones.

## Required on Every Page
- Sticky footer bar with: "If you are in crisis, call or text 988 (US) or text HOME to 741741"
- Footer links: Home, Blog, Find an Expert, Crisis Resources, Privacy Policy, Terms of Service

## Pages to Build

### 1. Crisis Resources Page (BUILD THIS FIRST)
- Simple, calming design
- Large clear heading: "You are not alone. Help is available right now."
- Cards for: 988 Suicide and Crisis Lifeline (call or text 988), Crisis Text Line (text HOME to 741741), International Association for Suicide Prevention (https://www.iasp.info/resources/Crisis_Centres/)
- Soft sage green background, no alarming colors
- No login required, always publicly accessible

### 2. Homepage
- Hero section: headline "A calm place to understand your mind. Find expert help when you're ready.", subheadline, two CTA buttons: "Read Free Articles" and "Find an Expert"
- Three feature highlights: Free Blog, Expert Directory, Crisis Support
- Recent blog posts section (3 cards)
- How it works section (3 steps)
- Trust signals: licensed experts, private and secure, no commitments

### 3. Blog Index Page
- Grid of article cards: title, category tag, short excerpt, read more link
- Filter buttons by category: Anxiety and Stress, Depression Awareness, Work and Burnout, Relationships, Therapy 101, Self-Care and Habits, Crisis and Support
- Pagination

### 4. Single Blog Post Page
- Title, author, date, category tag
- Full content area with comfortable reading width (700px max)
- Sidebar: related articles, find an expert CTA
- Crisis resources reminder at bottom of every post

### 5. Expert Directory Page
- Grid of expert cards: photo placeholder, name, specialty tags, session price, Book Session button
- Filter by specialty
- Search by name

### 6. Single Expert Profile Page
- Hero: photo, name, title, specialties, session price
- Full bio section
- Qualifications and license info
- Embedded Cal.com booking widget (placeholder for now)
- Stripe payment link button

### 7. Sign Up Page
- Email and password only
- Connected to Supabase auth
- Link to login page
- Disclaimer: "By signing up you agree to our Terms of Service and Privacy Policy"

### 8. Login Page
- Email and password
- Connected to Supabase auth
- Link to sign up page
- Forgot password link

### 9. User Dashboard
- Upcoming sessions (placeholder)
- Saved articles
- Account settings (update email, password)
- Logout button

### 10. About Page
- Mission statement
- How MindQuilt works (3 steps)
- Who the experts are
- Trust and safety section
- Key disclaimers:
  - MindQuilt is not a crisis service
  - Blog content is educational only, not medical advice
  - Experts are independent licensed professionals, not employees of MindQuilt
  - MindQuilt does not provide diagnosis or treatment

### 11. Expert Application Form Page
- Fields: full name, email, license type (dropdown), license number, country and state, years of experience, specialties (checkboxes), session price per hour, short bio
- Save to Supabase table called expert_applications
- Confirmation message after submit

## Database Tables Needed in Supabase
- users (handled by Supabase auth)
- blog_posts: id, title, slug, category, excerpt, content, author, published_date, published (boolean)
- experts: id, name, title, bio, specialties, license_type, license_number, session_price, cal_username, photo_url, verified (boolean)
- expert_applications: id, full_name, email, license_type, license_number, country, state, years_experience, specialties, session_price, bio, submitted_at
- saved_articles: id, user_id, blog_post_id, saved_at
