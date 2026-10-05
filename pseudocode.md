# Personal Budget Tracker - Pseudocode

Module main()

    Declare Real designIncome = 0
    Declare Real codingIncome = 0
    Declare Real documentationIncome = 0

    Declare Real softwareExpense = 0
    Declare Real equipmentExpense = 0
    Declare Real workspaceExpense = 0

    Declare Integer choice
    Declare Integer category
    Declare Real amount
    Declare Real totalIncome
    Declare Real totalExpenses
    Declare Real netBalance

    Do

        Display "=========================================="
        Display "        PERSONAL BUDGET TRACKER"
        Display "=========================================="
        Display "1. Log Income"
        Display "2. Log Expense"
        Display "3. View Financial Summary"
        Display "4. Exit"
        Display "Enter your choice (1-4):"
        Input choice

        While choice < 1 OR choice > 4
            Display "Invalid. Choice must be 1, 2, 3, or 4. Try Again:"
            Input choice
        End While

        If choice == 1 Then

            Display "--- INCOME MENU ---"
            Display "1. Design"
            Display "2. Coding"
            Display "3. User Documentation"
            Display "Enter income category:"
            Input category

            While category < 1 OR category > 3
                Display "Invalid. Please enter 1, 2, or 3. Try Again!"
                Input category
            End While

            Display "Enter income amount ($):"
            Input amount

            While amount < 0
                Display "Invalid. Please enter amount >= 0:"
                Input amount
            End While

            If category == 1 Then
                Set designIncome = designIncome + amount
                Display "Successfully added income for Design."

            Else If category == 2 Then
                Set codingIncome = codingIncome + amount
                Display "Successfully added income for Coding."

            Else
                Set documentationIncome = documentationIncome + amount
                Display "Successfully added income for User Documentation."
            End If

        Else If choice == 2 Then

            Display "--- EXPENSE MENU ---"
            Display "1. Software"
            Display "2. Equipment"
            Display "3. Workspace"
            Display "Enter expense category:"
            Input category

            While category < 1 OR category > 3
                Display "Invalid. Please enter 1, 2, or 3. Try Again!"
                Input category
            End While

            Display "Enter expense amount ($):"
            Input amount

            While amount < 0
                Display "Invalid. Please enter amount >= 0:"
                Input amount
            End While

            If category == 1 Then
                Set softwareExpense = softwareExpense + amount
                Display "Successfully added expense for Software."

            Else If category == 2 Then
                Set equipmentExpense = equipmentExpense + amount
                Display "Successfully added expense for Equipment."

            Else
                Set workspaceExpense = workspaceExpense + amount
                Display "Successfully added expense for Workspace."
            End If

        Else If choice == 3 Then

            Set totalIncome = designIncome + codingIncome + documentationIncome
            Set totalExpenses = softwareExpense + equipmentExpense + workspaceExpense
            Set netBalance = totalIncome - totalExpenses

            Display "=========================================="
            Display "           FINANCIAL SUMMARY"
            Display "=========================================="
            Display "Total Income: $", totalIncome
            Display "Total Expenses: $", totalExpenses
            Display "Net Balance: $", netBalance

            If netBalance > 0 Then
                Display "You are profitable this month!"

            Else If netBalance < 0 Then
                Display "You have a loss this month."

            Else
                Display "You broke even this month."
            End If

        End If

    While choice != 4

    Display "Thank you for using Personal Budget Tracker. Goodbye!"

End Module
