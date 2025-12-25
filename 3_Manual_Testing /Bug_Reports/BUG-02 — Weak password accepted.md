
## Title: Weak password is accepted during registration

**Environment:**
Chrome, macOS

**Preconditions:**
User is on the Registration page.

**Steps to Reproduce:**
1. Open the Registration page.
2. Enter a weak password (e.g., 12345).
3. Confirm the same password.
4. Enter valid personal details in all required fields.
5. Click Register.
   
**Actual Result:**
Account is created using a weak password.

**Expected Result:**
The system should enforce password-strength rules and display a validation message.

**Severity:**  High

**Priority:**  High
