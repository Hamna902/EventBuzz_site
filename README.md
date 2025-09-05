# EventBuzz - Event Booking Website 🎉

## Overview 📝

EventBuzz is a vibrant event booking platform designed to help users plan and book unforgettable events like weddings, birthdays, corporate dinners, and graduation parties. 🌟 The website features a modern, responsive design with sections for services, gallery, pricing, reviews, and contact. Users can browse packages, submit bookings with personal details, and send feedback via a contact form. All bookings and messages are securely stored in a MySQL database for easy management. 🗃️

The site offers user-friendly navigation, stunning sliders (powered by Swiper.js), and reliable data handling with PHP and MySQL. 💻 Payment is handled post-event via cash, as noted on the confirmation page. 💸

## Features ✨

- **Home Section**: A captivating hero slider showcasing event images with a catchy tagline. 🖼️
- **Services Section**: Highlights services like invitation design, photography, entertainment, vehicles, venues, and catering. 🎨📸🎶
- **About Section**: Details the company’s expertise in crafting memorable events. ℹ️
- **Gallery Section**: Displays event photos with interactive hover effects. 📷
- **Pricing Section**: Lists event packages (e.g., Wedding, Birthday, Official Dinner, Graduation) with details and a "Book Now" button linking to a booking form. 💰
- **Reviews Section**: A slider with glowing customer testimonials. 🌟
- **Contact/Feedback Section**: A form for users to send messages, stored in the database, with success/error feedback. 📩
- **Booking System**: Users select a package, enter details (username, phone, city, time, event date), and confirm bookings, with data saved in the database and a confirmation page displayed. ✅
- **Responsive Design**: Mobile-friendly layout with a hamburger menu for smaller screens. 📱
- **Database Integration**: Stores bookings (username, phone, city, event date, package name) and contact messages (name, email, phone, subject, message). 🗄️
- **No Online Payment**: Bookings confirm with a note that payment is due post-event via cash. 🧾

## Technologies Used 🛠️

- **Frontend**: HTML5, CSS3 (custom styles in `style.css`), JavaScript (Swiper.js for sliders, custom menu toggle in `script.js`). 🌐
- **Backend**: PHP (for form handling and database interactions). 🖥️
- **Database**: MySQL (database name: `eventbuzz_site` with tables `bookings` and `messages`). 🗃️
- **External Libraries**:
  - Swiper.js (v11) for sliders. 🖼️
  - Font Awesome (v6.7.1) for icons. 😊
  - Google Fonts (Poppins) for typography. ✍️
- **Server Requirements**: PHP-enabled server (e.g., XAMPP/WAMP), MySQL database. 🖥️

## Installation 🚀

### Prerequisites
- PHP 7+ (with MySQLi extension). 🐘
- MySQL server. 🗄️
- Web server (e.g., Apache via XAMPP). 🌐
- Web browser for testing. 🖥️

### Steps
1. **Clone or Download the Repository**:
   ```bash
   git clone https://github.com/Hamna902/EventBuzz_site.git
   ```
   Or download the ZIP file and extract it. 📥

2. **Set Up the Database**:
   - Create a new MySQL database named `eventbuzz_site`. 🗄️
   - Run the following SQL queries to create the required tables:
     ```sql
     CREATE TABLE bookings (
         id INT AUTO_INCREMENT PRIMARY KEY,
         username VARCHAR(255) NOT NULL,
         phone VARCHAR(50) NOT NULL,
         city VARCHAR(100) NOT NULL,
         event_date DATE NOT NULL,
         package_name VARCHAR(255) NOT NULL
     );

     CREATE TABLE messages (
         id INT AUTO_INCREMENT PRIMARY KEY,
         name VARCHAR(255) NOT NULL,
         email VARCHAR(255) NOT NULL,
         phone VARCHAR(50) NOT NULL,
         subject VARCHAR(255) NOT NULL,
         message TEXT NOT NULL
     );
     ```
   - Update database credentials in `db_connection.php`, `confirmation.php`, `process.php`, and `submit_contact.php` if needed (default: host=`localhost`, user=`root`, password=``, db=`eventbuzz_site`). 🔧

3. **Place Files on Server**:
   - Move the project folder to your web server’s root directory (e.g., `htdocs` in XAMPP). 📂
   - Ensure images (e.g., `images/home1.jpg`, etc.) are in the correct `images/` folder. 🖼️

4. **Start the Server**:
   - Launch XAMPP/WAMP and start Apache and MySQL. 🚀
   - Access the site at `http://localhost/eventbuzz_site/index.php` (replace `eventbuzz_site` with your folder name). 🌐

## Usage 🎈

1. **Browsing the Site**:
   - Navigate to the home page (`index.php`). 🏠
   - Use the top menu to explore sections like Services, Gallery, Pricing, etc. 🧭
   - On mobile, click the hamburger icon to toggle the menu. 🍔

2. **Booking an Event**:
   - In the Pricing section, click "Book Now" on a package (e.g., Wedding Package). 💍
   - This redirects to `login.php` (booking form) with the package name pre-filled (hidden field). 📋
   - Fill in username, phone, city, time, and event date. 📅
   - Submit to process the booking via `process.php`, which inserts data into the `bookings` table. ✅
   - On success, view the confirmation page (`confirmation.php`) with booking details and a payment note. 🎉

3. **Sending Feedback**:
   - In the Contact section, fill out the form (name, email, phone, subject, message). ✉️
   - Submit to `submit_contact.php`, which inserts into the `messages` table. 📬
   - Redirects back to `index.php` with a success indicator (no visible message by default; can be customized). ✅

4. **Viewing Confirmations**:
   - After booking, a styled confirmation page shows the user’s details and a success message. 🎊

## Folder Structure 📂

```
eventbuzz_site/
├── images/              # Event images for sliders, gallery, reviews, etc. 🖼️
├── confirmation.php     # Booking confirmation handler and display ✅
├── db_connection.php    # Database connection script 🗄️
├── index.php            # Main homepage with all sections 🏠
├── login.php            # Booking form (collects user details for booking) 📋
├── process.php          # Processes booking form and inserts into DB ⚙️
├── script.js            # JS for menu toggle and Swiper sliders 🎠
├── style.css            # Custom CSS styles 🎨
├── submit_contact.php   # Handles contact form submissions 📩
└── README.md            # This file 📝
```

## License 📜

Created by Hamna Nazar. All rights reserved. ©