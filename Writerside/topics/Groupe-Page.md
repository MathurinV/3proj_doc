# Groupe-page

This is a group page of 3PROJ project. It is a component of Vue.js that allows the user upload an expense and see the expenses of the group, pay the expenses, and see the group's statistics.


## Introduction
The group page in MoneyMinder serves as a central location for users to manage group expenses, refunds, and member transactions. This documentation provides an overview of the features, layout, and usage instructions for the group page.

## Layout

The group page is divided into four main sections: expenses, refunds, last transactions, and group details.

##  Components

The group page is composed of the following components:
- AppGroupes : the main component that contains the group's expenses, the group's refunds, the last transactions visualization and the group's members
- AppExpense : the component that allows the user to upload an expense and proof
- AppRefund : the component that allows the user to pay an expense and visualize the balance of all members in the group
- AppLastTransactions : the component that allows the user to see the last transactions of the group and sort them by date, amount, or member
- AppGroupDetails : the component that allows the user to see the group's statistics and the group's members with their information

### AppExpense

This component is composed of a form to create an expense then a form to upload the proof of the expense.
- A form to upload an expense with the following fields:
  - The amount of the expense
  - The description of the expense
  - The members who participated in the expense: the user can select one or more members from the group and preview the amount each member owes.

### AppRefund
This component is divided into two parts:
- The first part is a chart that shows the balance of all members in the group
- The second part is a list of refunds to pay with the following elements:
  - The amount of the refund
  - The member who has to receive the refund
> Payments are optimized to minimize the number of transactions between members, but the user can owe in some cases money to several members.
{style="note"}
### AppLastTransactions
This component is composed of the following elements:
- A list of the last transactions of the group with the following elements:
  - The date of the transaction
  - The amount of the transaction
  - The member who made the transaction
  - The member who received the transaction
  - The description of the transaction
  - Users can also update the proof of the transaction.
  - Users can download sum up of the transactions.

  >The user can sort the transactions by date, amount, or member.
  
  


### AppGroupDetails
This component is composed of the list of the group's members with the following elements:
- The name of the member
- The email of the member
- The balance of the member
- The last transaction of the member




## Usage Instructions



1. **Uploading an Expense**:
    - Click on the "Expenses" tab to view the group's expenses.
    - Fill in the required fields (amount, description, and members) and click "Submit" to save the expense.
    - The expense will be added to the group's expenses list and the balance of the members will be updated accordingly.
    - The user can then upload the proof of the expense by clicking on the "Upload Proof" button.

2. **Paying a Refund**:
    - Click on the "Refunds" tab to view the group's refunds.
    - Choose the refund to pay and click on Paypal or RIB to pay the refund:
        - If the user chooses Paypal, the user will be redirected to the Paypal website to complete the payment.
        - If the user chooses RIB, the user will see the RIB of the member who has to receive the refund. He must confirm the payment by clicking on the "Confirm Payment" button.
      > If the user who may the refund has not uploaded his RIB, the user will see a message that the user has not uploaded his RIB.
4. **Viewing Last Transactions**:
    - Click on the "Last Transactions" tab to view the group's last transactions.
    - The user can sort the transactions by date, amount, or member.
    - The user can update the proof of the transaction by clicking on the "Update Proof" button.
    - The user can see the proof of the transaction by clicking on the "Proof" button.
    - The user can see the balance of all members in the group by clicking on the "Balance" button.
4. **Viewing Group Details**:
    - Click on the "Group Details" tab to view the group's statistics and members.
    - The user can see the group's statistics, including the total expenses, total refunds, and total balance.
    - The user can see the list of group members with their information.
    - The user can see the balance of each member in the group.
    - The user can see the last transaction of each member in the group.
    - The user can update the picture of the group by clicking on the "Update Picture" button.
   