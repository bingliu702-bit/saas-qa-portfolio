# Day 18 - State Transition Test Scenarios

**Test Website:** https://the-internet.herokuapp.com/dynamic_controls

## SC-031: Verify Input Field Changes from Disabled to Enabled

**Scenario:** Verify that a disabled input field becomes enabled after clicking the Enable button.

**Initial State:** Disabled

**Event:** Click Enable

**Expected Next State:** Enabled

### Steps

1. Open the Dynamic Controls page.
2. Click the Enable button.
3. Wait until the input field becomes enabled.
4. Enter "QA State Test" in the input field.

### Expected Result

The input field should become enabled and accept text.

### Actual Result

The input field became enabled and accepted the text "QA State Test".

The button changed to "Disable", and the message "It's enabled!" was displayed.

### Status

Pass

## SC-032: Verify Input Field Changes from Enabled to Disabled

**Scenario:** Verify that an enabled input field becomes disabled after clicking the Disable button.

**Initial State:** Enabled

**Event:** Click Disable

**Expected Next State:** Disabled

### Steps

1. Open the Dynamic Controls page.
2. Click the Enable button.
3. Wait until the input field becomes enabled.
4. Enter "QA State Test" in the input field.
5. Click the Disable button.
6. Wait until the input field becomes disabled.
7. Attempt to enter "123" in the input field.

### Expected Result

The input field should become disabled and reject any new text input.

### Actual Result

The input field became disabled and retained the text "QA State Test".

The button changed to "Enable", and the message "It's disabled!" was displayed.

The input field did not accept any new text.

### Status

Pass


## SC-033: Verify Checkbox Removal and Restoration

**Scenario:** Verify that a checkbox can be removed and added again.

**Initial State:** Checkbox present

**Events:** Click Remove, then click Add

**Expected State Transitions:** Present → Removed → Present

### Steps

1. Open the Dynamic Controls page.
2. Select the checkbox.
3. Click the Remove button.
4. Wait until the checkbox disappears.
5. Click the Add button.
6. Wait until the checkbox reappears.

### Expected Result

The checkbox should disappear after clicking Remove, and the button should change to Add.

After clicking Add, the checkbox should reappear, and the button should change back to Remove.

### Actual Result

After clicking Remove, the checkbox disappeared, the button changed to Add, and the message "It's gone!" was displayed.

After clicking Add, the checkbox reappeared, the button changed to Remove, and the message "It's back!" was displayed.

The reappeared checkbox was unchecked.

### Status

Pass
