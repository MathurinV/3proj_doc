# Pages_Mobile


The Following Flowchart is detailing the organization of the app pages :
```mermaid
flowchart
	subgraph s1["Login"]
	end
	s1 --- n1["Home"]
	s1["Login Page"] --- n3["Register"]
	n1 --- n4
	n1 --- n5["User Stats"]
	n4["Group Details"] --- n2["Expense Details"]
	n4 --- n6["User Details"]
```

We used `navigation compose` to control navigation in the app

in Addition, here are the routes of the app :

```Kotlin
object Routes {
    const val HOME = "home"
    const val REGISTER = "register"
    const val LOGIN = "login"
    const val GROUP_DETAILS = "groupDetails"
    const val USER_DETAILS = "userDetails"
    const val EXPENSE_DETAILS = "expenseDetails"
    const val USER_STATS = "userStats"
}
```