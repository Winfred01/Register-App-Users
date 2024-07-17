# User Registration Validation System

## Introduction
This document describes a Python script designed to validate user registration data. The script includes comprehensive checks for user names, email addresses, and passwords to ensure they meet specific standards before registering the user in the system.

## Functions

### `validate_name(name: str) -> bool`
Validates that the provided name is a string with more than two characters.
- **Arguments**:
  - `name`: The name to validate.
- **Returns**:
  - `bool`: `True` if the name is valid, `False` otherwise.

### `validate_email(email: str) -> bool`
Validates that the email address is in a correct format, contains more than one character before the '@' symbol, includes an '@' symbol, and ends with one of the allowed top-level domains.
- **Arguments**:
  - `email`: The email to validate.
- **Returns**:
  - `bool`: `True` if the email is valid, `False` otherwise.

### `validate_password(password: str) -> bool`
Checks if the password is at least 9 characters long, includes at least one uppercase letter, and at least one digit.
- **Arguments**:
  - `password`: The password to validate.
- **Returns**:
  - `bool`: `True` if the password meets the criteria, `False` otherwise.

### `validate_user(name: str, email: str, password: str) -> bool`
Validates all user input fields by calling the individual validation functions.
- **Arguments**:
  - `name`: User's name.
  - `email`: User's email address.
  - `password`: User's password.
- **Returns**:
  - `bool`: `True` if all inputs are valid, `False` otherwise.

### `register_user(name: str, email: str, password: str) -> Union[dict, bool]`
Registers the user if all input validations pass, otherwise returns `False`.
- **Arguments**:
  - `name`: User's name.
  - `email`: User's email address.
  - `password`: User's password.
- **Returns**:
  - `dict`: A dictionary with user information if registration is successful.
  - `bool`: `False` if any validation fails.

## Example Usage
Below are some examples of how to use the script:

```python
# Example of successful registration
successful_registration = register_user("John Doe", "john.doe@example.com", "Secure123Password")
print(successful_registration)

# Example of failed registration
failed_registration = register_user("Jane", "jane@example.co.uk", "12345")
print(failed_registration)
