Exchange Online Mail Flow Troubleshooting
Problem

Users are unable to send or receive emails in Exchange Online.

Symptoms
Emails remain in Outbox
External users cannot receive messages
NDR (Non-Delivery Report) messages are generated
Investigation Steps
Step 1: Verify Microsoft 365 Service Health
Open Microsoft 365 Admin Center
Navigate to Health → Service Health
Check for any Exchange Online incidents
Step 2: Check MX Records

Use the following command:

nslookup -type=mx yourdomain.com

Verify the MX record points to Exchange Online.

Step 3: Perform Message Trace
Open Exchange Admin Center
Navigate to Mail Flow → Message Trace
Search using sender or recipient address
Root Cause

The domain MX record was pointing to an old mail gateway.

Resolution

Updated the MX record to the Microsoft 365 target value and allowed DNS propagation.

Validation
Test email delivery internally
Test email delivery externally
Confirm successful message trace
References
Microsoft Learn Documentation
Exchange Online Message Trace Guide
