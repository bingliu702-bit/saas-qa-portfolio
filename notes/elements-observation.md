# Day 08 — HTML Elements Observation

## 1. Element Observation

| # | Page Element | HTML Tag | Key Attributes | Page Purpose |
|---|---|---|---|---|
| 1 | Username field | `input` | `type="text"`, `name="username"`, `id="username"` | Allows the user to enter a username. |
| 2 | Password field | `input` | `type="password"`, `name="password"`, `id="password"` | Allows the user to enter a password. |
| 3 | Login button | `button` | `class="radius"`, `type="submit"` | Allows the user to submit the login form. |
| 4 | GitHub ribbon image | `img` | `src="/img/forkme_right_green_007200.png"`, `alt="在 GitHub 上 fork 我"` | Displays the GitHub fork ribbon image. |
| 5 | Option 1 checkbox | `input` | `type="checkbox"`, `data-testid="ui-checkbox-option1"`, `id="ui-checkbox-option1"`, `class="form-check-input"` | Allows the user to select or deselect Option 1. |
| 6 | Radio 1 button | `input` | `type="radio"`, `name="radioGroup"`, `data-testid="ui-radio-Radio 1"`, `id="ui-radio-Radio 1"`, `value="Radio 1"` | Allows the user to select Radio 1 from the radio button group. |
| 7 | Country/Region dropdown | `select` | `data-testid="ui-single-dropdown"`, `id="singleDropdown"`, `class="form-control"` | Allows the user to select a country or region from the dropdown menu. |
| 8 | USA option | `option` | `value="USA"` | Allows the user to select the United States from the dropdown menu. |
| 9 | Navbar brand link | `a` | `href="/"`, `class="navbar-brand-modern navbar-brand"` | Allows the user to navigate to the website's home page. |
| 10 | Click button | `input` | `type="button"`, `id="ui-click-button"`, `data-testid="ui-click-button"`, `class="btn btn-primary"` | Allows the user to trigger an action by clicking the button. |

## 2. New Test Scenarios

### SC-013: Verify Option 1 Checkbox Selection

**Test Objective:**  
Verify that the Option 1 checkbox can be selected and that the page output correctly reflects the selection.

**Preconditions:**  
- The target test page is accessible.
- The Option 1 checkbox is visible and initially unchecked.

**Steps:**
1. Open the target test page.
2. Locate the Option 1 checkbox.
3. Click the Option 1 checkbox.
4. Observe the checkbox state and the page output.

**Expected Result:**  
The Option 1 checkbox is displayed as selected, and the page output correctly shows that Option 1 has been selected.

---

### SC-014: Verify Country/Region Dropdown Selection

**Test Objective:**  
Verify that the user can select United States from the Country/Region dropdown and that the page output correctly reflects the selection.

**Preconditions:**  
- The target test page is accessible.
- The Country/Region dropdown is visible.
- No country or region is initially selected.

**Test Data:**  
United States

**Steps:**
1. Open the target test page.
2. Locate the Country/Region dropdown.
3. Open the dropdown.
4. Select United States.
5. Observe the selected option and the page output.

**Expected Result:**  
United States is displayed as the selected option, and the page output correctly shows United States.
