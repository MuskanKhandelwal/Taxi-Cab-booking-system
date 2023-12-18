# Taxi Cab Booking System

A digital platform connecting passengers with drivers for on-demand transportation services. This system allows users and drivers to log in/sign up, request rides, serve rides, make payments, etc., ensuring a seamless transport experience.

## Tools Used
- Python
- Flask
- MySQL
- HTML
- CSS

## Used Pages for Scraping Data
- [Cars.com - Research](https://www.cars.com/research/)
- [HyreCar - Cars for Uber & Lyft](https://www.hyrecar.com/cars-uber-lyft/)

## Database Design

### Application Flow and Data Interaction
1. **Registration and Login:**
   - Users and drivers register on their respective signup pages.
   - Data entered in the forms is sent to the server (`app.py`), processed, and stored in the database.
   - For login, the application verifies credentials against the database.

2. **Booking Trips:**
   - Users book trips through a booking interface.
   - Booking details are sent to the server, which calculates fares and stores trip information in the database.

3. **Payment Processing:**
   - After a trip, the user is directed to the payment page.
   - Payment details are entered, processed by the server, and recorded in the database.

4. **Viewing Trip History:**
   - The customer history page retrieves and displays a list of past trips for the user.
   - The server queries the database for the user's trip history and sends this data back for display.

5. **Driver Operations:**
   - Drivers log in on the driver login page to access their dashboard.
   - The driver home page displays upcoming trips and earnings, retrieved from the database.
   - The driver history page lists past trips, details, and earnings, fetched from historical trip data in the database.
   - View Assignments: Check upcoming trips on the home page.
   - Complete Trips: After finishing trips, details are updated in the system.

6. **Customer Operations:**
   - Customer Home Page (`customer_home.html`):
     - Purpose: Main interface for customers to initiate trip bookings.
     - Functionality: Offers options to input trip details like pickup and dropoff locations and the number of riders.
     - Data Interaction: Data entered by the customer is sent to the backend. A query inserts rider details into `Rider_details` and trip requests into `Trip_requests`. The backend interacts with an external API to calculate the trip distance and estimate the fare.

7. **Booking Process:**
   - Flow: Upon submitting trip details on the customer home page, `app.py` processes the request.
   - Data Interaction: Involves calculating the estimated fare, potentially using external APIs or internal logic, selecting a driver, and creating a new entry in the `Trip_requests` table with all relevant details. The system retrieves and stores data in various tables like `Rider_details`, `Trip_requests`, and potentially `Pickup_time_estimation`. It ensures the trip details are accurately recorded in the database, ready for the driver to accept and proceed with the trip.

   This flow indicates a well-structured system where customer inputs are efficiently processed and integrated into the taxi booking database, ensuring a seamless booking experience.

### Overall System Overview
- The application uses Flask (`app.py`) as the backend to handle requests from various HTML pages.
- Processes user input, interacts with the database for data retrieval and storage.
- Serves the processed data back to the frontend for display, resulting in a seamless flow for both users and drivers.
- Users and drivers can register, log in, book trips, make payments, and view their respective histories.
- Data is consistently exchanged between the frontend and backend, ensuring real-time updates and accurate information for both users and drivers.
