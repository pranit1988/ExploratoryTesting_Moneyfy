# ExploratoryTesting_Moneyfy
## Exploratory testing charters to document your testing.

List of ideas/bullet points of what should be tested in monefy application. List of test cases is representing the app structure. Every statement is a test. 

* App Home screen should display header. /High/
    * Menu button should open left side-menu
        * Left side menu should allow selection of a money space for displaying
        * Left side menu should allow selection of time period for transactions displaying.
        * It should be possible to open New expense window while left-side menu is open
        * It should be possible to navigate through the header buttons
    * App Logo should be displayed in the middle of the header. Under the logo the current money space is displayed
    * Double-arrow button should open New transfer screen
        * New transfer screen should have a "Back arrow button" to return to Home screen
        * New transfer screen should have active input of transaction ammount
        * New transfer screen should display current date in format "Weekday, DD Month"
        * New transfer screen should have Add note input
        * New transfer screen should have button to invoke onscreen numeric keyboard
            * Numeric onscreen keyboard should have Add transfer button
        * New transfer screen should give possibility to select between the money space to transfer from
        * New transfer screen should give possibility to select between the money space to transfer to
        * It should be possible to add new transfer transaction via Add Transfer button
            * New transfer screen should be closed
            * Toast message should appear with Cancel button
            * Transfer transactions are displayed in Balance history section
    * Vertical elipsis button should open Right-side menu
        * Right-side menu should display Categories, Accounts and Currencies menu items.
        * Tap on each menu item opens sub-menu
            * Categories sub-menu should allow user to add custom Category (Pro-Feature)
            * Tap on item from the categories list opens Edit category screen
                * Edit category screen should allow user to delete category
                * It should be possible to Merge categories
                * It should be possible to distinguish between Enabled and disabled categories
                * It should be possible to edit category name
                * It should be possible to change category icon (Pro-Feature)
                * Changes should be saved automatically
                * It should be possible to close Edit category screen via back arrow button
                * Toast message should appear. Message should confirm that the changes in category were saved. It should be possible to delete new category via Cancel button in toast.
            * Accounts sub-menu should  allow user to create new Account
                * New account screen should allow user to give account name
                * New account screen should allow user to select currency (Pro-Feature)
                * New account screen should allow user to setup custom currency rate (Pro-Feature)
                * New account screen should allow user to setup Initial account balance and Initial balance date
                * New account screen should allow user to define whether new account balance should be Included in the total balance
                * New account screen should allow user to select Account icon
                * Add button in the header of New account screen should create an account. Toast message appears. Message should confirm that the changes in account were saved. It should be possible to delete new account via Cancel button in toast.
            * Accounts sub-menu should allow editing accounts
                * Edit account screen repeats New account window
                * Edit account screen should allow user to delete account
                * Edit account screen should allow user to merge accounts
                * Edit account screen should allow user to enable/disable account
            * Accounts sub-menu should allow creating transfer transaction
            * Currencies (Pro-Feature) [...]
* Check if the "circle diagram" is built correctly /Low/
* App Home screen should display Category actions. /High/
* Category actions buttons should open "New expense" screen /High/
    * New expense screen should have a "Back arrow button" to return to Home screen
    * New expence screen shout display current date in format "Weekday, DD Month"
    * New expence screen should have active input of transaction ammount
        * It should be possible to clear input value using "backspace" button
        * It should be possible to see transaction currency next to transaction ammount input
        * It should be possible to enter transaction ammount using the onscreen numeric keyboard
        * Onscreen numeric keyboard should be displayed on the load of the screen meaning that the transaction ammount input is active
        * It should be impossible to skip transaction ammount input (zero value is not accepted)
        * Input value should be validated
        * It should be impossible to perform mathematical operations in transaction input /BUG/
        * It should be possible to enter values with comma /BUG/
    * New expence screen should have input to "Add note" to transaction
        * Tapping on the "Add note" input displays onscreen character keyboard
        * It should be possible to enter n characters in note
        * It should be possible to finish typing note by tapping on green checkmakr button. Onscreen character keyboard is closed. "Add note" input should be inactive /BUG/
    * New expense screen should display onscreen numeric keyboard
        * Onscreen numeric keyboard should influence only transaction ammount input
        * Onscreen numeric keyboard should have a proper layout
    * New expenses screen should have button ADD '[CATEGORY NAME]'
        * Tapping on ADD button, if the transaction ammount is zero, highlights transaction ammount input
        * Tapping on ADD button with valid transaction ammount and any valid or empty note value creates "Expense transaction". New expense window is closed.
        * It should be possible to Cancel the transaction. For that after creating transaction the pop-up message should appear. The pop-up message should confirm the transaction. There should be Cancel button in the pop-up message. Cancel button deletes transaction. Pop-up message disappears after 10 sec.
* App Home screen should display Balance button
    * Balance button should display current balance (positive/negative; with currency; display two decimals)
    * Balance button should change it's color depending on the total balance
    * Tap on Balance button should display Balance section
        * Balance section displays history of transactions of the predefined time period
        * Transactions list is displayed by Categories.
        * Every Category has a total value of transactions found in this Category
        * Tap on Category expands list of transactions. Each transaction displays if it's debit or credit. Every transaction in a list displays transaction ammount with currency and the transaction date "DD Mon"
    * Second tap on Balance button hides the Balance section
* App Home screen should display -/+ fab buttons /Medium/
    * Tap on - fab button opens New expense screen
    * Tap on + fab button opens New income screen.
        * *New Income screen repeats layout of New Expense screen with the following difference*:
            * Before confirmation of the transaction user should select transaction category. Tap on Choose Category button to see available income categories.
            * It should be impossible to Choose Category while the transaction ammount is zero.
            * It should be possible to add custom income category. (Pro-Feature)
            * Once the income category is selected positive transaction is created. New income screen is closed. Toast message is displayed. It is possible to delete new transaction via Cancel button on toast.
        * Balance button is updated after income transaction was created. Transaction is displayed in Balance history section.
* Pro-Feature screen should appear every time a button with Pro-Feature is tapped.
    * Pro-Feature screen should display big CTA button to initiate purchase of unlimited use
    * Pro-Feature screen should display a list of features available after purchase of unlimited use

## Findings from your charters. Did everything work as expected? What bugs were discovered?

* Overall Monefy is an useful app to manage daily/monthly/yearly expenses for any individual by creating account using simple app UI.
* Most of the app features are working fine but some needs enhancement done to fix issues observed.
* There were few bugs discovered as explained below during exploratory testing

## Bugs discovered during Exploratory Testing of Moneyfy App

* When I input money for expense/income and leave “add note” field empty, then go for choosing category , I can’t switch back to add note.Instead of it, I need to recreate “add expense”.
* No cryptocurrencies found and no ability to add “our own” currency
* No native synchronization of history, only Dropbox and Google Drive.
* User is prompted to pay for switching to Dark mode
* It does not allow to reorder or mark items paid if you pay early so you remember not to pay them again.
* It does not show you your running balance. Only the overall balance for the time frame is selected.

## Prioritisation of those charters - which area of the app or testing would you explore first and why?
   # Below are key areas of the app to be tested in ascending order of priority
   
* App Home screen should display header.
* Menu button should open left side-menu
* It should be possible to navigate through the header buttons
* Double-arrow button should open New transfer screen
* New transfer screen should have active input of transaction ammount
* New transfer screen should have button to invoke onscreen numeric keyboard
* Numeric onscreen keyboard should have Add transfer button
* New transfer screen should give possibility to select between the money space to transfer from
* New transfer screen should give possibility to select between the money space to transfer to
* It should be possible to add new transfer transaction via Add Transfer button
* New transfer screen should be closed
* Vertical elipsis button should open Right-side menu
* Accounts sub-menu should allow creating transfer transaction
* App Home screen should display Category actions.
* Category actions buttons should open "New expense" screen
* New expence screen should have active input of transaction ammount
* It should be possible to enter transaction ammount using the onscreen numeric keyboard
* It should be impossible to skip transaction ammount input (zero value is not accepted)
* Input value should be validated
* New expense screen should display onscreen numeric keyboard
* Onscreen numeric keyboard should influence only transaction ammount input
* New expenses screen shoult have button ADD '[CATEGORY NAME]'
* Tapping on ADD button, if the transaction ammount is zero, highlights transaction ammount input
* App Home screen should display -/+ fab buttons
* Tap on - fab button opens New expense screen
* Tap on + fab button opens New income screen.
* It should be impossible to Choose Category while the transaction ammount is zero.
* Balance button is updated after income transaction was created. Transaction is displayed in Balance history section.

## How much time you have planned for each charter?
   * 
