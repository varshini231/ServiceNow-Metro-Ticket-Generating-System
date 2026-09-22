# ServiceNow Metro Ticket Generating System

## Project Overview

The Metro Ticket Generating System is a ServiceNow-based application developed to simplify the process of booking metro tickets. The system allows users to select the source and destination stations, travel date, journey type, number of passengers, and payment mode.

The application calculates the ticket fare based on the selected route, journey type, and number of passengers. It also provides QR code functionality for the generated metro ticket.

## Objectives

- To develop a simple metro ticket booking system using ServiceNow.
- To provide source and destination station selection.
- To calculate the ticket fare automatically.
- To support single and return journeys.
- To calculate fares based on the number of passengers.
- To provide different payment options.
- To generate QR code information for the metro ticket.
- To control access to the metro station table using ACLs.

## Technologies Used

- ServiceNow
- Service Catalog
- Catalog Client Scripts
- Catalog UI Policies
- Service Portal
- JavaScript
- Access Control Lists (ACLs)
- Update Sets

## System Components

### 1. Metro Station Details

A custom table named `u_metro_station_detail` is used to store metro station information.

The station name is configured as the display field so that station names are displayed when selecting source and destination stations.

### 2. Book A Metro Ticket

A Service Catalog Item named `Book A Metro Ticket` is created for metro ticket booking.

The catalog item contains the following variables:

- Starting From
- Going To
- Travel Date
- Type of Journey
- No of Passengers
- Mode of Payment
- Enter Payment Mode
- Amount for Single Journey
- Amount Including Return
- QR Generated

### 3. Fare Calculation

The fare is calculated automatically using a Catalog Client Script.

The calculation depends on the selected source station, destination station, journey type, and number of passengers.

For a single journey:

`Total Fare = Route Fare × Number of Passengers`

For a return journey:

`Total Fare = Route Fare × 2 × Number of Passengers`

Example:

Ameerpet to Madhapur has a route fare of ₹30.

For 2 passengers on a single journey:

`₹30 × 2 = ₹60`

For 2 passengers on a return journey:

`₹30 × 2 × 2 = ₹120`

### 4. Catalog Client Script

The catalog client script `Fare auto-calculation` is used to calculate the ticket amount automatically.

The script contains the configured route fares and calculates the amount according to the selected journey type and passenger count.

### 5. Catalog UI Policy

A Catalog UI Policy named `Fields Visibility` is configured for the ticket booking form.

The policy controls the visibility of the payment-related fields based on the selected payment option.

### 6. Service Portal QR Widget

A Service Portal widget named `Metro QR Widget` is created for displaying the metro ticket QR code.

The widget contains HTML, client-side JavaScript, and server-side script components.

The QR information can contain details such as:

- Source station
- Destination station
- Travel date
- Number of passengers
- Journey type

### 7. Access Control

Access Control Lists are configured for the `u_metro_station_detail` table.

The configured operations include:

- Create
- Read
- Write
- Delete

These ACLs restrict direct access to the database table while allowing users to interact with the application through the appropriate interface.

## Fare Details

The project includes configured fares for different metro station routes.

Some of the configured routes include:

| Route | Fare |
|---|---:|
| Ameerpet - Panjagutta | ₹20 |
| Ameerpet - Madhapur | ₹30 |
| Ameerpet - Jubilee Hills | ₹20 |
| Ameerpet - Kukatpally | ₹30 |
| Ameerpet - LB Nagar | ₹50 |
| Ameerpet - Uppal Stadium | ₹60 |
| Panjagutta - Madhapur | ₹30 |
| Panjagutta - Jubilee Hills | ₹20 |
| Jubilee Hills - Madhapur | ₹30 |
| Madhapur - Kukatpally | ₹40 |
| Kukatpally - LB Nagar | ₹60 |
| LB Nagar - Uppal Stadium | ₹30 |

The same fare is applied for the reverse direction of a route.

## ServiceNow Configuration

The project configuration includes:

- Custom Metro Station table
- Service Catalog Item
- Catalog Variables
- Catalog Client Script
- Catalog UI Policy
- Catalog UI Policy Action
- Service Portal Widget
- Access Control Lists
- Update Set

## Update Set

The ServiceNow configuration is captured in an Update Set named:

`Metro Ticket Generating System`

The exported Update Set XML is included in this repository.

The XML contains captured ServiceNow configuration related to the project, including catalog variables, client scripts, UI policies, Service Portal widget configuration, and ACL configuration.

## Project Screenshots

The following screenshots can be added to document the project:

1. Metro Station Details table
2. Book A Metro Ticket catalog item
3. Ticket booking form
4. Automatic fare calculation
5. Payment mode selection
6. QR code
7. Catalog Client Script
8. Catalog UI Policy
9. Service Portal Widget
10. ACL configuration
11. Generated request

## Project Demo

Demo Video:

(https://drive.google.com/file/d/1c3eVF8vUETkj3IwmABY0fNacdqdCG487/view?usp=sharing)

## Future Enhancements

The system can be extended with the following features:

- Online payment integration
- Ticket cancellation
- Booking history
- Automated email notifications
- Approval workflow
- Metro card recharge
- Reporting and dashboards
- Real-time metro service information
