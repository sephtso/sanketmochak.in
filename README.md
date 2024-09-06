# sanketmochak.in (Social Media Investigator)
A comprehensive tool for parsing and analyzing social media data
![image](https://github.com/user-attachments/assets/ca1fd300-a1e2-4b6f-ba78-83ce425fbc5d)

Overview: A tool for automatically parsing social media feeds, extracting relevant information, and generating documented evidence in the form of screenshots.

Addressing the Problem: Provides law enforcement with an automated, efficient way to track, parse, and analyze social media data in real-time, helping in combating cyberterrorism and misinformation.

Innovation and Uniqueness:
Combines API-based data retrieval with browser automation (Selenium) for platforms that lack APIs.
Uses Puppeteer/Playwright for automated screenshot generation.
Features a user-friendly dashboard for viewing and analyzing the data.

#TECH STACKS
Backend: Django, Django REST Framework, Celery (for asynchronous tasks), Selenium, Puppeteer/Playwright.
Frontend: React.js, Chart.js/D3.js for data visualization.
Database: PostgreSQL/MySQL.
Implementation Methodology:
Phase 1: Database setup and authentication.
Phase 2: API integration for social media platforms (Facebook, Twitter, Instagram).
Phase 3: Data parsing and cleaning.
Phase 4: Frontend and data visualization using React.
Phase 5: Screenshot generation for evidence and integration with dashboard.
Phase 6: Testing and deployment.

FLOW DIAGRAM
[User Interaction]
        |
        v
[Frontend: React.js Application]
        |
        |--[API Request (Axios)]-->
        |
[Backend: Django REST Framework]
        |
        v
[Social Media Post APIs Endpoints]
        |
        |--[Fetch/Store Data]-->
        |     (Facebook, Twitter, etc.)
        |
    [PostgreSQL Database]
        |
        v
[Data Storage/ Retrieval]
        |
        |--[Asynchronous Processing]-->
        |
[Celery Worker (asynchronous tasks)]
        |
        v
[Real-Time Data Parsing & Cleaning]
        |
        v
[Store Clean Data in Database]
        |
        |--[Browser Automation]-->
        |
[Selenium/Playwright for Screenshots]
        |
        v
[Store Evidence Screenshots in Storage]
        |
        v
[Frontend (Display Data & Visualize)]

DETAILED FLOW DIAGRAM
Frontend (React.js):

User Interaction: The user interacts with a React.js web app (e.g., a dashboard).
API Request: The app sends requests (via Axios) to the backend, asking for data (social media posts).
Data Visualization: Visualize the fetched data using Chart.js or D3.js.
Backend (Django REST Framework):

API Endpoints: Django REST API endpoints provide access to social media posts (e.g., /api/posts/).
Post Requests: Collect and store user data (e.g., social media feeds) from the frontend.
Database (PostgreSQL):

Data Storage: All posts are stored in a PostgreSQL database. Models like SocialMediaPost store platform-specific data such as post content, user info, and timestamps.
Social Media API Integration:

API Fetching: The backend interacts with social media platforms (e.g., Facebook, Twitter) using their respective APIs to fetch posts.
Asynchronous Tasks (Celery):

Data Processing: Asynchronous tasks, using Celery and Redis, fetch data from the social media APIs in the background to avoid slowing down the main API endpoints.
Data Cleaning & Parsing: The fetched data is cleaned and normalized before being stored back in the database.
Browser Automation (Selenium/Playwright):

Screenshot Generation: For platforms that don’t have API access (e.g., Instagram), Selenium or Playwright is used for automating the browser to capture screenshots of posts as evidence.
Frontend (React):

Data Display: Cleaned data and screenshots are sent to the frontend, where users can view posts and evidence via a user-friendly React dashboard.
Step-by-Step Flow:
User Requests Data: The user initiates a request on the frontend to fetch or view data.
Frontend Sends API Call: React app sends an API request to the Django backend to retrieve posts or trigger new fetches from social media platforms.
Backend Handles Request: Django REST API processes the request.
Fetch Social Media Data: The backend either fetches new data from social media APIs or retrieves stored data from the database.
Asynchronous Processing: Celery tasks run in the background to fetch and parse social media posts.
Browser Automation: If necessary, browser automation captures screenshots of posts that APIs can’t provide.
Data Stored in Database: The parsed data (and screenshots, if any) are stored in the PostgreSQL database.
Frontend Displays Data: The backend returns the cleaned data, which is rendered on the React dashboard, possibly visualized with Chart.js or D3.js.




