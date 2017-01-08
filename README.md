# Przykładowy tekst


## Core tests
### CORE-001 User is able to register when he put correct data

*ID*: CORE-001

*Name*: User is able to register when he put correct data

*Priority* (high/medium/low): high

*Description*: We want to be sure that system in typical correct situation is working correct. Put correct data and expect that user will be able to register.

*Preconditions*: Database of users is empty

*Steps*:

1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

2. Press "Register" button

*Expected*:

+ "User is registered" page is visible.
+ Correct user data are visible in admin logs or database.
