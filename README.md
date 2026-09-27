# ServiceNow Metro Ticket Generating System

## Project Overview

The Metro Ticket Generating System is a ServiceNow-based application developed to simplify the process of booking metro tickets.

The system allows users to select the starting station, destination station, journey type, number of passengers, and payment mode. The application automatically calculates the ticket fare based on the selected route, journey type, and number of passengers.

The system also provides QR code generation for the metro ticket through a Service Portal widget.

## Objectives

- To develop a simple metro ticket booking system using ServiceNow.
- To provide starting and destination station selection.
- To calculate the ticket fare automatically.
- To support single and return journeys.
- To calculate fares based on the number of passengers.
- To provide different payment options.
- To generate a QR code for the metro ticket.
- To provide a simple and user-friendly ticket booking interface.

## Technologies Used

- ServiceNow
- Service Catalog
- Catalog Client Scripts
- Catalog UI Policies
- Service Portal
- Service Portal Widgets
- JavaScript
- Update Sets

## System Components

### 1. Metro Station Selection

The `Book A Metro Ticket` catalog item provides dropdown fields for selecting the starting and destination stations.

Available stations include:

- Ameerpet
- Madhapur
- LB Nagar
- Uppal Stadium
- Jubilee Hills
- Panjagutta
- Kukatpally

The user can select the required starting station and destination from the available options.

### 2. Book A Metro Ticket

A Service Catalog Item named `Book A Metro Ticket` is created for metro ticket booking.

The catalog item contains the following variables:

- Starting From
- Going To
- Type of Journey
- No of Passengers
- Amount for Single Journey
- Amount Including Return
- Mode of Payment
- Enter Payment Mode

### 3. Type of Journey

The system supports two types of journeys:

- Single Journey
- Return Journey

For a single journey, the fare is calculated based on the selected route and number of passengers.

For a return journey, the route fare is calculated for both directions.

### 4. Number of Passengers

The user can select the number of passengers from 1 to 5.

The total fare is automatically calculated according to the selected number of passengers.

### 5. Fare Calculation

The fare is calculated automatically using a Catalog Client Script.

The calculation depends on:

- Starting station
- Destination station
- Journey type
- Number of passengers

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

### 6. Catalog Client Script

The catalog client script `Fare auto-calculation` is used to calculate the ticket amount automatically.

The script contains the configured route fares and calculates the amount according to the selected journey type and passenger count.

### 7. Payment Mode

The system provides payment mode options for the ticket booking process.

Available payment options include:

- UPI
- Card
- Others

The `Enter Payment Mode` field is controlled using a Catalog UI Policy.

### 8. Catalog UI Policy

A Catalog UI Policy named `Fields Visibility` is configured for the ticket booking form.

The policy controls the visibility and mandatory behavior of the payment-related field.

### 9. QR Code Generation

The system provides QR code generation when the user selects `Order Now`.

The QR code contains metro ticket information such as:

- Starting station
- Destination station
- Number of passengers
- Journey type

The QR code is generated using a QR code service and displayed through the Metro QR Widget.

### 10. Service Portal QR Widget

A Service Portal widget named `Metro QR Widget` is used to display the generated metro ticket QR code.

The widget contains:

- HTML
- Client-side JavaScript
- Server-side JavaScript

The widget displays the QR code in the Service Portal interface.

## Fare Details

The project includes configured fares for different metro station routes.

| Route | Fare |
|---|---:|
| Ameerpet - Panjagutta | ₹20 |
| Ameerpet - Madhapur | ₹30 |
| Ameerpet - Jubilee Hills | ₹20 |
| Ameerpet - Kukatpally | ₹30 |
| Ameerpet - LB Nagar | ₹50 |
| Ameerpet - Uppal Stadium | ₹60 |
| Panjagutta - Jubilee Hills | ₹20 |
| Panjagutta - Madhapur | ₹30 |
| Panjagutta - Kukatpally | ₹40 |
| Panjagutta - LB Nagar | ₹50 |
| Panjagutta - Uppal Stadium | ₹60 |
| Jubilee Hills - Madhapur | ₹30 |
| Jubilee Hills - Kukatpally | ₹40 |
| Jubilee Hills - LB Nagar | ₹50 |
| Jubilee Hills - Uppal Stadium | ₹60 |
| Madhapur - Kukatpally | ₹40 |
| Madhapur - LB Nagar | ₹50 |
| Madhapur - Uppal Stadium | ₹50 |
| Kukatpally - LB Nagar | ₹60 |
| Kukatpally - Uppal Stadium | ₹70 |
| LB Nagar - Uppal Stadium | ₹30 |

The same configured fare is applied for the reverse direction of a route.

## ServiceNow Configuration

The project configuration includes:

- Service Catalog Item
- Catalog Variables
- Question Choices
- Catalog Client Scripts
- Catalog UI Policy
- Catalog UI Policy Action
- Service Portal Widget
- QR Code Generation
- Update Set

## Update Set

The complete project configuration is captured in the following Update Set:

`Metro Ticket Generating System Project`

The exported Update Set XML contains the required ServiceNow configuration for the metro ticket booking system, including:

- Catalog Item
- Catalog Variables
- Question Choices
- Fare Calculation Script
- QR Generation Script
- Catalog UI Policy
- Catalog UI Policy Action
- Service Portal QR Widget

The Update Set XML can be imported into another ServiceNow instance through Retrieved Update Sets.

## Project Workflow

The basic workflow of the application is:

1. Open the `Book A Metro Ticket` catalog item.
2. Select the starting station.
3. Select the destination station.
4. Select the journey type.
5. Select the number of passengers.
6. Select the payment mode.
7. The system automatically calculates the ticket fare.
8. Click `Order Now`.
9. The system generates the metro ticket QR code.
10. The QR code can be scanned at the metro station gate.

## Testing

The system was tested with different station combinations, journey types, and passenger counts.

Example test:

- Starting From: Ameerpet
- Going To: Madhapur
- Journey Type: Single Journey
- Number of Passengers: 2

Expected Fare:

`₹30 × 2 = ₹60`

For Return Journey:

`₹30 × 2 × 2 = ₹120`

QR code generation was also tested through the Service Portal.

## Project Demo

[Demo Video](https://drive.google.com/file/d/1c3eVF8vUETkj3IwmABY0fNacdqdCG487/view?usp=sharing)

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

## Project Author

Amreen

## Project

ServiceNow Metro Ticket Generating System
