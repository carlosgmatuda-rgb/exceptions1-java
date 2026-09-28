# Hotel Reservation

A simple Java console program that manages a hotel reservation. It reads the reservation data, displays it along with its duration in nights, and allows the dates to be updated with input validation.

## How it works

1. The user enters the **room number**, **check-in date** and **check-out date**.
2. The program displays the reservation, including its duration in nights.
3. The user then enters new check-in and check-out dates to update the reservation.
4. The program displays the updated reservation.

### Validation rules

- Reservation updates are only allowed for **future dates**.
- The check-out date must be **after** the check-in date.

If any rule is violated, the program shows an error message instead of updating the reservation.

## Class diagram

```
Reservation
-----------------------------------
- roomNumber : Integer
- checkin    : Date
- checkout   : Date
-----------------------------------
+ duration() : Integer
+ updateDates(checkin : Date, checkout : Date) : void
```

## Examples

**Successful update**

```
Room number: 8021
Check-in date (dd/MM/yyyy): 23/09/2019
Check-out date (dd/MM/yyyy): 26/09/2019
Reservation: Room 8021, check-in: 23/09/2019, check-out: 26/09/2019, 3 nights

Enter data to update the reservation:
Check-in date (dd/MM/yyyy): 24/09/2019
Check-out date (dd/MM/yyyy): 29/09/2019
Reservation: Room 8021, check-in: 24/09/2019, check-out: 29/09/2019, 5 nights
```

**Invalid dates (check-out before check-in)**

```
Room number: 8021
Check-in date (dd/MM/yyyy): 23/09/2019
Check-out date (dd/MM/yyyy): 21/09/2019
Error in reservation: Check-out date must be after check-in date
```

**Invalid update (dates not in the future)**

```
Room number: 8021
Check-in date (dd/MM/yyyy): 23/09/2019
Check-out date (dd/MM/yyyy): 26/09/2019
Reservation: Room 8021, check-in: 23/09/2019, check-out: 26/09/2019, 3 nights

Enter data to update the reservation:
Check-in date (dd/MM/yyyy): 24/09/2015
Check-out date (dd/MM/yyyy): 29/09/2015
Error in reservation: Reservation dates for update must be future dates
```

## How to run

```bash
javac Main.java
java Main
```

## Technologies

- Java
