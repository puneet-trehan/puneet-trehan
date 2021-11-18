### Mobile application testing on iOS

### Mission: Exploring non-pro features of monefy application

### Objective: To check if the user can add records

### Oracles:

1. Reading through [monefy website](https://monefy.me/)

### Risks:

1. An application might not work
2. A blocker might stop the navigation

### Environment Setup:

1. Install an application on iOS

### Heuristics:

1. Goldilocks
2. Errors
3. Responsiveness

### Test Charter 1:

Should explore:

- add expense and income from +/- fab buttons
- add expense through category actions from the home screen
- design layout of the home screen

Time should spend no more than 40 min 

Priority is deemed high because it is the most critical aspect of the application

### Testing Notes:

Pre-requisites: Application must be installed successfully 

A list of ideas/bullet points of what should be tested in monefy application. A list of test cases is representing the app structure. Every statement is a test.

**App home screen should display**

- Left side on header
    1. Monefy cash logo
    2. Filter
- Right side on header
    1. Search 
    2. Two-way arrow
    3. Vertical ellipsis 
- Body
    1. A circle diagram and inside circle diagram
        - Income and currency in green color
        - Expenses and currency in red color
    2. A meaning full category actions in the form of icons of different shapes and colors surrounding the circle diagram
- Footer
    1. Balance
    2. -/+ fab buttons
- Check if the "circle diagram" is built correctly
- Category actions on home screen /High/
- Category actions buttons should open the "New expense" screen
    - The new expense screen should have a "Cancel" to return to the Home screen
    - The new expense screen shout display the current date in the format "Weekday, DD Month"
    - The new expense screen should have active input of transaction amount
        - It should be possible to clear input value using the "backspace" button
        - It should be possible to see transaction currency next to transaction amount input
        - It should be possible to enter transaction amount using the onscreen numeric keyboard
        - The on-screen numeric keyboard should be displayed on the load of the screen
        - It should be impossible to skip transaction amount input (zero value is not accepted)
        - The input value should be validated
        - It should be possible to perform mathematical operations in a transaction
    - The new expense screen should have input to "Add Note" to the transaction
        - Tapping on the "Add note" input displays mobile character keyboard
        - It should be possible to enter any characters in the note
        - It should be possible to finish typing notes by selecting done on the keyboard. The onscreen character keyboard is closed.
    - The new expense screen should display the on-screen numeric keyboard
        - The on-screen numeric keyboard should influence only transaction amount input
        - The on-screen numeric keyboard should have a proper layout
    - New expenses screen should have button ADD '[CATEGORY NAME]'
        - Tapping on the ADD button, if the transaction amount is zero, highlights transaction amount input
        - Tapping on ADD button with the valid transaction amount and any valid or empty note value creates "Expense transaction"
            - The user navigated to the home screen
                - toast message should appear which confirms the transaction
                    - user can undo the action by selecting undo in the toast text
            - The Balance amount should get changed in the balance section as well as in the "circular diagram"
- **App Home screen should display Balance button**
    - The balance button should display the current balance (positive/negative; with currency; display two decimals)
    - The balance button should change its color depending on the total balance
        - If expenses are less than income, it should display a green color
        - If expenses are more than income, it should display red color
    - Tap on the Balance button should display the Balance section
        - The Balance section displays the history of transactions of the predefined time period
        - Transactions list is displayed by categories
        - Every category has a total value of transactions found in this Category
        - Tap on category expands the list of transactions
            - Each transaction displays if it's debit or credit
                - The red dot that appears next to the amount shows credit or expense
                - The green dot that appears next to the amount shows debit or income
            - Every transaction in a list displays the transaction amount with currency and the transaction date "DD Mon"
        - Filter options with descending date/amount
    - The second tap on the Balance button hides the Balance section
- App Home screen should display -/+ fab buttons
    - Tap on - fab button opens New expense screen
    - Tap on the + fab button to open the New income screen.
        - *New Income screen repeats layout of New Expense screen with the following difference*:
            - Before confirmation of the transaction user should select the transaction category. Tap on Choose Category button to see available income categories.
            - It should be impossible to Choose a Category while the transaction amount is zero.
            - It should be possible to add a custom income category. (Pro-Feature)
            - Once the income category is selected positive transaction is created.
                - User navigated to home screen
                    - toast message should appear which confirms the transaction
                        - user can undo the action by selecting undo in the toast text
                - The Balance amount should get changed in the balance section as well as in the "circular diagram"
        - The balanced button is updated after the income transaction was created. The transaction is displayed in the Balance history section.
        - The pro-Feature screen should appear every time a button with Pro-Feature is tapped.
            - The pro-Feature screen should display a big CTA button to initiate the purchase of unlimited use
            - The pro-Feature screen should display a list of features available after purchase of unlimited use

### Test Charter 2:

Should explore 

- Filter button
- Vertical ellipse and its sub-categories

Time should spend no more than 40 min 

Priority is deemed medium because it is the basic part of the application which does not have much impact on the business

### Testing Notes:

Pre-requisites: Application must be installed successfully 

A list of ideas/bullet points of what should be tested in monefy application. A list of test cases is representing the app structure. Every statement is a test.

- **Filter button should open left side-menu**
    - The left side menu should allow selection of an account/cash
        - On any selection change, the left menu close, and automatic navigation to the home screen
    - The left side menu should allow the selection of time period for transactions displaying.
    - It should be possible to open the New expense window while the left-side menu is open
    - It should be possible to navigate through the header buttons
- **Two-way arrow button should open New transfer screen**
    - It should have a "Cancel" to return to the previous screen
    - It should have active input of transaction amount
        - Selection of this field brings an onscreen numeric keypad
    - It should have an "Add" note input
        - Selection of this invoke mobile character keyboard
        - The user can add any character
        - Select on done on the keyboard and back button must close the keyboard
    - It should have a button to invoke an on-screen numeric keypad
        - Numeric onscreen keypad have
            - The "Save" button at bottom of the calculator
            - "Back" button at the top left corner, to close the numeric keypad
            - "Add" note input
    - Two fields which indicate a transfer from and transfer to, selection of these fields invokes a list of values
        - 'from' and 'to' fields should not have the same values, otherwise onscreen keypad doesn't work
        - It is possible to save the transfer on a selection of save buttons, then the user is navigated to a home screen with the toast message at the bottom
            - Transfer transactions are displayed in the circle diagram section
            - Toast messages automatically disappear after some seconds or on selection
            - Action can be undone by tapping on undo in the toast message and the save transaction disappears from the circle diagram
    - The vertical ellipsis button should open the Right-side menu
        - It should display Categories, Accounts, Currencies, and Settings menu items
        - Tap on each menu item opens sub-menu
            - Categories sub-menu should allow users to add custom Category (Pro-Feature)
            - Tap on an item from the categories list opens Edit category screen
                - It should have in the header
                    - Done button on the left corner
                        - Navigate the user to the last screen
                    - Edit Screen text
                    - Trash icon should delete a category
                        - It should delete the category
                            - A confirmation message box open
                                - With confirmation and suggestion text with two buttons "Yes" and "Cancel"
                                    - Selection of "Yes" delete the category and throws the user out to the home screen with toast text to undo
                                        - Undo will undo the action and record do not delete
                                    - Cancel close the confirmation box
                    - Vertical ellipses, which brings three actions on the bottom of the screen to Disable, Merge and Cancel
                        - Disable/Enable
                            - Should disable the category and user remains in the same screen
                            - Users can enable the category by tapping on the vertical ellipses select "Enable" which is changed from "Disable"
                        - Merge
                            - Open the list of categories to merge
                            - Select category user is thrown to a home screen with the toast text which confirms the action
                                - undo should undo the changes
                        - Cancel should close the options and no change in the screen
                        - It should be possible to distinguish between Enabled and disabled categories
                - It should have in the body an editable input field with a default name of the selected category
                    - Select this field open the mobile character keyboard
                        - The user should be able to change the name
                        - Select done on the keyboard close the keyboard
                    - Select "Done" from the top left
                        - The user is navigated to the home screen
                            - toast text should appear which confirms the changes are saved
                            - undo should undo the changes
                - It should be possible to change the category icon (Pro-Feature)
            - Accounts sub-menu should allow users to create new Account
                - It should allow the user to give an account name
                - It should allow users to select currency (Pro-Feature)
                - It should allow users to set up custom currency exchange rates (Pro-Feature)
                - It should allow users to set up the initial account balance and Initial balance date
                - It should allow users to define whether a new account balance should be included in the total balance
                - The new account screen should allow the user to select the Account icon
                - Add button in the header of the New account screen should create an account.
                    - The user is navigated to the home screen
                        - toast message should appear which confirms the changes are saved
                        - undo should undo the changes
            - Accounts sub-menu should allow account edit
                - It repeats New account window
                - It should allow users to delete the account
                - It should allow users to merge accounts
                - It should allow users to enable/disable the account
            - Currencies (Pro-Feature) [...]
            - Settings should allow the user to change the application overall settings
                - Users can change the balance with three types of modes budget, carryover, and future recurring records
                - Unlock Monefy (Pro-Feature)
                - Dark Theme (Pro-Feature)
                - Users can change any language from the list. Once select, the list of languages get open for the user selection, upon selection
                    - It closes the list, and language is changed for the application
                - Users can change the currency of the app. Once select, the list of currencies get open for the user selection, upon selection
                    - It changes the app currency
                    - Navigates the user to the home screen
                    - A toast text message which confirms the selection
                        - Undo in the toast message to undo the selection
                - Users can change the First Day of the Week. Once selected, the list of days open for user selection, upon selection
                    - It throws the user to the home screen
                - Passcode protection (Pro-Feature)
                - Review application navigates the user to the app store
                - Users can able to export their data into a file
                - Users can learn more about the application by selecting About Monefy, upon selection
                    - Opens the About Monefy box and the background becomes disabled
                    - Can be closed, by tapping outside the box and on OK
                    - The privacy policy will redirect users to the website of monefy
                    - Enable/disable google analytics
                - Google drive (Pro-Feature)
                - Dropbox (Pro-Feature)
                - Data backup allows users to create, restore and clear the backups, upon selection
                    - Create: Allow the user to create a backup. Toast message confirms the backup file created
                    - Restore: Allow the user to restore from the created backup
                    - Clear: Delete all the stored backups

### Risk to mitigate:

1. The security and data privacy of the user, plus it should be GDPR complaint
2. The application should support the latest and the previous version of mobile operating systems like android and ios and different screen resolutions

### Bugs discovered:

1. Select on done on the keyboard and back button does not close the keyboard 
2. After selection of categories in Merge, a backup toast message is displayed
3. Enable is shown for all the categories only for disable category it should show

