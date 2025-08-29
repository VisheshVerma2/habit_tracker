
# Habit Tracker User Stories 

---

<!-- PART 1: AUTHENTICATION -->

## Epic: Authentication (Login & Registration)

| name                 | about                                                                                               | title                                  | labels         | assignees |
| -------------------- | --------------------------------------------------------------------------------------------------- | -------------------------------------- | -------------- | --------- |
| Account Registration | Register with name, username, age, and country to create an account.                               | `[AUTH] Account Registration`          | authentication |           |

---

## **Feature Description**

**Feature:** Account Registration

**As a** user  
**I need** to register with my name, username, age, and country  
**So that** I can create an account and access the habit tracking features.

---

## **Details and Assumptions**

* Registration form must include name, username, age, and country fields.
* All required fields must be validated before submission.
* Duplicate usernames should not be allowed.
* No password is required at registration; login is restricted to default credentials.
* Users should be redirected to the login page upon successful registration.

---

## **Acceptance Criteria**

```gherkin
Given that I am on the registration page
When I enter valid name, username, age, and country
And I submit the form
Then my account should be created successfully
And I should see a confirmation message
And I should be redirected to the login page
````

---

| name          | about                                                             | title                  | labels         | assignees |
| ------------- | ----------------------------------------------------------------- | ---------------------- | -------------- | --------- |
| Account Login | Log in using default username and password to access the account. | `[AUTH] Account Login` | authentication |           |

---

## **Feature Description**

**Feature:** Account Login

**As a** user
**I need** to log in using the default username and password
**So that** I can access my account and track my habits.

---

## **Details and Assumptions**

* Login page must have username and password fields.
* Users can only log in with predefined default credentials.
* Credentials must not be stored in the browser cache and must be cleared after logout.
* Users cannot log in with their registered credentials.
* Successful login redirects to the homepage.

---

## **Acceptance Criteria**

```gherkin
Given that I am on the login page
When I enter the default username and password
And I submit the form
Then I should be logged in successfully
And I should be redirected to the homepage
```

---

| name                    | about                                                              | title                         | labels         | assignees |
| ----------------------- | ------------------------------------------------------------------ | ----------------------------- | -------------- | --------- |
| Error Feedback on Login | Display error message for incorrect username or password at login. | `[AUTH] Login Error Feedback` | authentication |           |

---

## **Feature Description**

**Feature:** Login Error Feedback

**As a** user
**I need** to receive an error message when I enter the wrong username or password
**So that** I know my login attempt was unsuccessful.

---

## **Details and Assumptions**

* Error message should not reveal whether the username or password is incorrect.
* Entered credentials should remain in the form for correction.
* User can attempt login again without reloading the page.

---

## **Acceptance Criteria**

```gherkin
Given that I am on the login page
When I enter an incorrect username or password
And I submit the form
Then I should see an error message stating that the credentials are incorrect
And my entered data should remain in the fields for correction
```

---

<!-- PART 2: HOMEPAGE -->

## Epic: Homepage

| name                     | about                                                              | title                                 | labels   | assignees |
| ------------------------ | ------------------------------------------------------------------ | ------------------------------------- | -------- | --------- |
| Personalized Welcome Msg | Display personalized welcome message with user’s name on homepage. | `[HOME] Personalized Welcome Message` | homepage |           |

---

## **Feature Description**

**Feature:** Personalized Welcome Message

**As a** user
**I need** to see a personalized welcome message with my name on the homepage
**So that** I feel recognized and can confirm I am logged into the correct account.

---

## **Details and Assumptions**

* Welcome message includes the registered name.
* Should display at the top of the homepage in a friendly tone.
* Name should be retained from registration even if login uses default credentials.

---

## **Acceptance Criteria**

```gherkin
Given that I am logged in
When I access the homepage
Then I should see a welcome message with my registered name at the top of the page
And if I log out and log back in, the correct name should still be displayed
```

---

| name               | about                                                  | title                       | labels   | assignees |
| ------------------ | ------------------------------------------------------ | --------------------------- | -------- | --------- |
| Progress Dashboard | Display current habit completion progress on homepage. | `[HOME] Progress Dashboard` | homepage |           |

---

## **Feature Description**

**Feature:** Progress Dashboard

**As a** user
**I need** to see my current habit progress on the homepage
**So that** I can track my daily and weekly completion rate at a glance.

---

## **Details and Assumptions**

* Progress should be visualized using a percentage bar or chart.
* Data should update automatically after a habit is completed.
* The dashboard should show both daily and weekly stats.

---

## **Acceptance Criteria**

```gherkin
Given that I have active habits
When I complete a habit
Then the progress dashboard should update automatically
And I should see the new percentage immediately
```

---

| name                  | about                                            | title                             | labels   | assignees |
| --------------------- | ------------------------------------------------ | --------------------------------- | -------- | --------- |
| Completed Habits List | Display completed habits separately on homepage. | `[HOME] Completed Habits Section` | homepage |           |

---

## **Feature Description**

**Feature:** Completed Habits Section

**As a** user
**I need** to see a list of my completed habits separately from my active habits
**So that** I can track what I have accomplished today.

---

## **Details and Assumptions**

* Completed habits should move automatically to the “Completed” section.
* Section should refresh without reloading the page.
* Data resets daily at midnight.

---

## **Acceptance Criteria**

```gherkin
Given that I have completed at least one habit today
When I refresh or return to the homepage
Then my completed habits should appear in the “Completed” section
And active habits should no longer appear there
```

---

<!-- PART 3: PROFILE PAGE -->

## Epic: Profile Page

| name         | about                                                                         | title                    | labels       | assignees |
| ------------ | ----------------------------------------------------------------------------- | ------------------------ | ------------ | --------- |
| View Profile | Display registered profile information including name, username, age, country | `[PROFILE] View Profile` | profile-page |           |

---

## **Feature Description**

**Feature:** View Profile

**As a** user
**I need** to view my profile details including name, username, age, and country
**So that** I can verify and review my personal information.

---

## **Details and Assumptions**

* Profile information should match the data entered during registration.
* Profile page should be accessible via a navigation menu or profile icon.
* Display format should be clean and easy to read.

---

## **Acceptance Criteria**

```gherkin
Given that I am logged in
When I navigate to my profile page
Then I should see my name, username, age, and country
And the data should match my registration information
```

---

| name         | about                                         | title                    | labels       | assignees |
| ------------ | --------------------------------------------- | ------------------------ | ------------ | --------- |
| Edit Profile | Update age and country from the profile page. | `[PROFILE] Edit Profile` | profile-page |           |

---

## **Feature Description**

**Feature:** Edit Profile

**As a** user
**I need** to edit my profile details for age and country
**So that** I can keep my information accurate and up to date.

---

## **Details and Assumptions**

* Only age and country are editable; name and username remain fixed.
* Form validation should ensure valid age input and country selection.
* Changes should be saved immediately after confirmation.

---

## **Acceptance Criteria**

```gherkin
Given that I am on my profile page
When I edit my age or country and save changes
Then the updated information should appear immediately
And the changes should persist after logging out and back in
```

---

| name                   | about                                                  | title                              | labels       | assignees |
| ---------------------- | ------------------------------------------------------ | ---------------------------------- | ------------ | --------- |
| Profile Picture Upload | Allow users to upload or change their profile picture. | `[PROFILE] Upload Profile Picture` | profile-page |           |

---

## **Feature Description**

**Feature:** Upload Profile Picture

**As a** user
**I need** to upload or change my profile picture
**So that** my profile has a personal visual identity.

---

## **Details and Assumptions**

* Supported formats: JPG, PNG.
* File size limit: 5 MB.
* Picture should display on the profile page and beside the username on the homepage.

---

## **Acceptance Criteria**

```gherkin
Given that I am on my profile page
When I upload a valid JPG or PNG file under 5MB
Then my profile picture should update immediately
And it should display on both the profile page and homepage
```

---

<!-- PART 4: HABITS PAGE -->

## Epic: Habits Page

| name          | about                                                 | title                    | labels | assignees |
| ------------- | ----------------------------------------------------- | ------------------------ | ------ | --------- |
| Add New Habit | Add a new habit with a name and optional description. | `[HABITS] Add New Habit` | habits |           |

---

## **Feature Description**

**Feature:** Add New Habit

**As a** user
**I need** to add a new habit with a name and optional description
**So that** I can track my activities and progress.

---

## **Details and Assumptions**

* Name is mandatory; description is optional.
* Habit list should update immediately after adding.
* Newly added habits appear in the active habits list.

---

## **Acceptance Criteria**

```gherkin
Given that I am on the habits page
When I enter a habit name and optional description
And I save the habit
Then the habit should appear in my active habits list
```

---

| name                | about                                 | title                          | labels | assignees |
| ------------------- | ------------------------------------- | ------------------------------ | ------ | --------- |
| Mark Habit Complete | Mark a habit as complete for the day. | `[HABITS] Mark Habit Complete` | habits |           |

---

## **Feature Description**

**Feature:** Mark Habit Complete

**As a** user
**I need** to mark habits as complete for the day
**So that** I can keep track of my progress.

---

## **Details and Assumptions**

* Completed habits move to the “Completed” section on homepage.
* Completion status resets daily.
* Visual confirmation of completion is required (e.g., checkmark icon).

---

## **Acceptance Criteria**

```gherkin
Given that I have an active habit
When I mark it as complete
Then it should disappear from my active habits list
And appear in the “Completed” section on the homepage
```

---

| name         | about                                     | title                   | labels | assignees |
| ------------ | ----------------------------------------- | ----------------------- | ------ | --------- |
| Delete Habit | Remove a habit permanently from the list. | `[HABITS] Delete Habit` | habits |           |

---

## **Feature Description**

**Feature:** Delete Habit

**As a** user
**I need** to delete habits from my list
**So that** I can remove unwanted or irrelevant activities.

---

## **Details and Assumptions**

* Deletion should require confirmation to avoid accidental loss.
* Deleted habits are removed permanently with no undo option.
* UI should update immediately after deletion.

---

## **Acceptance Criteria**

```gherkin
Given that I have an active habit
When I choose to delete it and confirm
Then it should be removed from my habit list permanently
```

---

<!-- PART 5: REPORTS PAGE -->

## Epic: Reports Page

| name                | about                                                           | title                       | labels  | assignees |
| ------------------- | --------------------------------------------------------------- | --------------------------- | ------- | --------- |
| View Weekly Reports | Display weekly overview of habit progress over the past 7 days. | `[REPORTS] Weekly Progress` | reports |           |

---

## **Feature Description**

**Feature:** View Weekly Reports

**As a** user
**I need** to see a summary of my habit progress for the past 7 days
**So that** I can understand how well I am maintaining my habits.

---

## **Details and Assumptions**

* Report should include progress percentage or summary cards.
* Data updates dynamically as habits are marked complete or missed.
* Motivational messages should be displayed based on progress.
* Clear distinction between completed and missed habits.

---

## **Acceptance Criteria**

```gherkin
Given that I have tracked habits over the past 7 days
When I view the reports page
Then I should see a summary of my weekly habit progress
And motivational messages based on my performance
```

---

| name                       | about                                                | title                              | labels  | assignees |
| -------------------------- | ---------------------------------------------------- | ---------------------------------- | ------- | --------- |
| Visualize Completed Habits | Show chart of completed habits per day for the week. | `[REPORTS] Completed Habits Chart` | reports |           |

---

## **Feature Description**

**Feature:** Visualize Completed Habits

**As a** user
**I need** to see a chart of how many habits I complete each day
**So that** I can identify trends in my habit consistency.

---

## **Details and Assumptions**

* Chart can be bar, line, or heatmap style.
* Interactive elements to view details per day.
* Colors clearly differentiate completed vs. incomplete.
* Accessibility features like text labels and high contrast.

---

## **Acceptance Criteria**


```gherkin
Given that I have completed habits during the week
When I view the completed habits chart
Then I should see a visual representation of completed habits per day
And I can tap a day to see details
```

---

| name                   | about                                                                | title                                    | labels  | assignees |
| ---------------------- | -------------------------------------------------------------------- | ---------------------------------------- | ------- | --------- |
| View All Habits Report | Show comprehensive list of completed and incomplete habits in report | `[REPORTS] Comprehensive Habit Overview` | reports |           |

---

## **Feature Description**

**Feature:** Comprehensive Habit Overview

**As a** user
**I need** to see all habits with their completion status and frequency
**So that** I have a full understanding of my habit tracking performance.

---

## **Details and Assumptions**

* User can sort or filter habits (completed/missed).
* Habit data persists between sessions.
* Optional streak counters for motivation.
* Layout must be clear and uncluttered.

---

## **Acceptance Criteria**

```gherkin
Given that I have tracked habits
When I view the comprehensive habits report
Then I should see all habits with their completion status and frequency
And I can filter or sort the list by status
```

---

<!-- PART 6: NOTIFICATIONS PAGE -->

## Epic: Notifications Page

| name                         | about                                  | title                                | labels        | assignees |
| ---------------------------- | -------------------------------------- | ------------------------------------ | ------------- | --------- |
| Enable/Disable Notifications | Toggle global notifications on or off. | `[NOTIFICATIONS] Manage Preferences` | notifications |           |

---

## **Feature Description**

**Feature:** Enable/Disable Notifications

**As a** user
**I need** to toggle notifications globally
**So that** I can choose whether to receive habit reminders.

---

## **Details and Assumptions**

* Toggle switch to enable or disable all notifications.
* Confirmation message on toggle change.
* When disabled, no reminders should be sent.

---

## **Acceptance Criteria**

```gherkin
Given that I am on the notifications settings page
When I toggle notifications off
Then I should receive confirmation
And no habit reminders should be sent until I toggle notifications back on
```

---

| name                            | about                                                  | title                           | labels        | assignees |
| ------------------------------- | ------------------------------------------------------ | ------------------------------- | ------------- | --------- |
| Select Habits for Notifications | Choose specific habits for which to receive reminders. | `[NOTIFICATIONS] Select Habits` | notifications |           |

---

## **Feature Description**

**Feature:** Select Habits for Notifications

**As a** user
**I need** to select which habits trigger notifications
**So that** I only get reminders for habits I am focusing on.

---

## **Details and Assumptions**

* List habits with checkboxes for notification enable/disable.
* Changes persist between sessions.
* Option to “Select All” for convenience.

---

## **Acceptance Criteria**

```gherkin
Given that I am on the notifications settings page
When I select or deselect habits for notifications
Then only selected habits should trigger reminders
And my selection should persist after logout and login
```

---

| name                         | about                                                    | title                                | labels        | assignees |
| ---------------------------- | -------------------------------------------------------- | ------------------------------------ | ------------- | --------- |
| Configure Notification Times | Set notification schedule (morning, afternoon, evening). | `[NOTIFICATIONS] Configure Schedule` | notifications |           |

---

## **Feature Description**

**Feature:** Configure Notification Schedule

**As a** user
**I need** to set times for receiving notifications (morning, afternoon, evening)
**So that** I get timely reminders throughout the day.

---

## **Details and Assumptions**

* Default suggested times (e.g., 8 AM, 2 PM, 7 PM) with ability to customize.
* Respect device “Do Not Disturb” settings.
* Confirmation message on saving schedule changes.

---

## **Acceptance Criteria**

```gherkin
Given that I am on the notifications settings page
When I set notification times for morning, afternoon, and evening
And I save my preferences
Then notifications should be sent at the selected times for enabled habits
And I should see confirmation of my changes
```

