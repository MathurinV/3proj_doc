# Groupe-page

This is a group page of 3PROJ project. It is a component of Vue.js that allows the user upload an expense and see the expenses of the group, pay the expenses, and see the group's statistics.


##  Components

The group page is composed of the following components:
- AppGroupes : the main component that contains the group's expenses, the group's refunds, the last transactions visualization and the group's members
- AppExpense : the component that allows the user to upload an expense and proof
- AppRefund : the component that allows the user to pay an expense and visualize the balance of all members in the group
- AppLastTransactions : the component that allows the user to see the last transactions of the group and sort them by date, amount, or member
- AppGroupDetails : the component that allows the user to see the group's statistics and the group's members with their information

### AppExpense

This component is composed of the following elements:
- A form to upload an expense with the following fields:
  - The amount of the expense
  - The description of the expense
  - The proof of the expense
  - The members who participated in the expense

### AppRefund
This component is divided into two parts:
- The first part is a chart that shows the balance of all members in the group
- The second part is a list of refunds to pay with the following elements:
  - The amount of the refund
  - The member who has to receive the refund
> Payments are optimized to minimize the number of transactions between members, but the user can owe in some cases money to several members.

### AppLastTransactions
This component is composed of the following elements:
- A list of the last transactions of the group with the following elements:
  - The date of the transaction
  - The amount of the transaction
  - The member who made the transaction
  - The member who received the transaction
  - The description of the transaction
  - The proof of the transaction
    The user can sort the transactions by date, amount, or member.
  Users can also update the proof of the transaction.


### AppGroupDetails
This component is composed of the list of the group's members with the following elements:
- The name of the member
- The email of the member
- The balance of the member
- The last transaction of the member