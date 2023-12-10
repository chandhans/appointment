# Appointment Booking Smart Contract

## Overview

The AppointmentBooking smart contract is a decentralized application (DApp) written in Solidity for the Ethereum blockchain. This contract facilitates the booking and cancellation of appointments. Each appointment slot is associated with an Ethereum address, representing the user who booked the appointment.

## Contract Details

### Owner

The `owner` variable represents the address that deployed the smart contract. This address has special privileges, such as the ability to deploy the contract and potentially perform administrative functions.

### Appointments Mapping

The `appointments` mapping associates each appointment slot (identified by a unique `uint256` value) with the Ethereum address of the user who booked that slot. A value of `address(0)` indicates that the slot is available for booking.

### Events

The contract emits two events:

- `AppointmentBooked`: Triggered when a user successfully books an appointment slot. The event includes the slot number and the user's Ethereum address.

- `AppointmentCanceled`: Triggered when a user cancels a previously booked appointment slot. The event includes the slot number and the user's Ethereum address.

## Functions

### `bookAppointment`

The `bookAppointment` function allows users to book an available appointment slot. The slot must be a positive integer, and the function checks whether the slot is already booked. If the slot is available, it is assigned to the user who called the function, and the `AppointmentBooked` event is emitted.

### `cancelAppointment`

The `cancelAppointment` function enables users to cancel a previously booked appointment. The slot is cleared, and the `AppointmentCanceled` event is emitted. The function checks whether the appointment was already canceled to prevent redundant cancellations.

### `isSlotBooked`

The `isSlotBooked` function allows users to check whether a specific appointment slot is already booked. It returns a boolean indicating the booking status of the given slot.

## Deployment

1. Deploy the smart contract to an Ethereum blockchain network using a compatible development environment.
2. The contract is initialized with the deploying address as the owner.

## Usage

- **Booking Appointments**: Users can book available appointment slots using the `bookAppointment` function.
- **Canceling Appointments**: Users can cancel previously booked appointments using the `cancelAppointment` function.
- **Checking Availability**: The `isSlotBooked` function can be used to check whether a specific slot is already booked.

## Security Considerations

- Ensure that the `owner` address is secure, as it holds administrative privileges.
- Users should be aware of gas costs associated with transactions, especially during periods of high network activity.

## Author

Chandhan S

chiidhii55@gmail.com
