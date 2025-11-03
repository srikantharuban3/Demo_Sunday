# Instruction 

- You are a test automation engineer.  
- Execute all test cases listed in the **"Test Suite"** section.  
- Use **Playwright MCP tools** to perform each test step.  
- If any step or verification fails, mark the **entire test case as failed**.  
- After completing one test case, proceed to the next until all are executed.  
- When all test cases are completed, generate a **Test Execution Report** in `.html` format.  
- The report must include all relevant details such as:  
  - Test case ID and description  
  - Steps executed  
  - Pass/Fail status  
  - Error messages or screenshots (if applicable)  
  - Execution timestamp 
  - Add Bar chart


# Test suite

## TC 001 - Verify that user can register a new customer

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Click on the Register link.
- Fill the registration page. 
- Use unique username and password. 
- user name should be 10 charactors and should be unique.
- submit the form by clicking on the register page. 
- Verify that welcome message with the new username is displayed.

## TC 002 - Verify user login functionality with valid credentials

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Enter valid username in the username field
- Enter valid password in the password field
- Click on the "Log In" button
- Verify that user is successfully logged in and account overview page is displayed
- Verify that "Welcome [username]" message is displayed

## TC 003 - Verify user can open a new account

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Enter valid username in the username field
- Enter valid password in the password field
- Click on the "Log In" button
- Click on "Open New Account" link
- Select account type as "SAVINGS"
- Click "Open New Account" button
- Verify new account created successfully.

## TC 004 - Verify account overview functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Accounts Overview" link
- Verify that account details are displayed
- Verify that account numbers are visible
- Verify that account balances are displayed

## TC 005 - Verify "Open New Account" functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Open New Account" link
- Select account type (Checking or Savings)
- Select funding account from dropdown
- Click on "Open New Account" button
- Verify that new account is created successfully
- Verify that account number is generated and displayed

## TC 006 - Verify "Transfer Funds" functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Transfer Funds" link
- Enter transfer amount
- Select "From Account" from dropdown
- Select "To Account" from dropdown
- Click on "Transfer" button
- Verify that funds transfer is completed successfully
- Verify that confirmation message is displayed

## TC 007 - Verify "Bill Pay" functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Bill Pay" link
- Fill payee information (name, address, city, state, zip code, phone, account number)
- Enter payment amount
- Select account to pay from
- Click on "Send Payment" button
- Verify that payment is processed successfully
- Verify that confirmation message is displayed

## TC 008 - Verify "Find Transactions" functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Find Transactions" link
- Select an account from dropdown
- Enter transaction ID or amount or date criteria
- Click on "Find Transactions" button
- Verify that matching transactions are displayed
- Verify that transaction details are accurate

## TC 009 - Verify "Update Contact Info" functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Update Contact Info" link
- Update contact information fields (first name, last name, address, city, state, zip code, phone)
- Click on "Update Profile" button
- Verify that contact information is updated successfully
- Verify that confirmation message is displayed

## TC 010 - Verify "Request Loan" functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Request Loan" link
- Enter loan amount
- Enter down payment amount
- Select account for down payment
- Click on "Apply Now" button
- Verify that loan application is submitted
- Verify loan approval or denial status is displayed

## TC 011 - Verify logout functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on "Log Out" link
- Verify that user is successfully logged out
- Verify that login page is displayed
- Verify that user session is terminated

## TC 012 - Verify navigation links functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Verify that "About Us" link works correctly
- Verify that "Services" link works correctly
- Verify that "Products" link works correctly
- Verify that "Locations" link works correctly
- Verify that "Contact Us" link works correctly
- Verify that all links navigate to appropriate pages

## TC 013 - Verify registration form validation

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Click on the Register link
- Leave all fields empty and click "Register" button
- Verify that appropriate validation messages are displayed
- Fill partial information and verify field-specific validations
- Verify that password confirmation validation works correctly

## TC 014 - Verify forgotten login information functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Click on "Forgot login info?" link
- Enter first name, last name, address, city, state, zip code, and SSN
- Click on "Find My Login Info" button
- Verify that login information retrieval process works
- Verify appropriate response message is displayed

## TC 015 - Verify account transaction history

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Click on an account number from accounts overview
- Verify that transaction history is displayed
- Verify that transaction dates, descriptions, and amounts are shown
- Verify that account balance is correctly calculated 