# Home Screen

The home screen is the main page to start with, it is divided in three parts : 

- Current user : on top of the screen, a clickable card to update user data, change profile picture, logout and a <code> Button() </code> to display user stats leading to the <a href="Stats-Screen.md"> Stats Screen </a> and another one to navigate to <a href="User-Payment-Screen.md"> User Payment Screen </a>, opened in a <code> modalBottomSheet() </code>.
- Then, a Pager with three pages :

  - Page 1 : Your current groups, displayed in a column that leads to the <a href="Group-Details-Screen.md"> group details screen </a> selected, with another <code> Button() </code> at the bottom to create a new group (opening a dialog).
  - Page 2 : Your invitations to groups, with two <code> Button() </code>, either refuse or accept the invitation.
  - Page 3 : Your private messages with other members on the app.

## images

<p>Main Page of groups</p>
<img src="home_screen.png" alt="home screen image"/>

<p>Current User Sheet</p>
<img src="current_user_sheet.png" alt="current user image"/>

<p> Invitations tab </p>
<img src="invitation_tab.png" alt="invitation tab image"/>

<p> create a group</p>
<img src="create_group.png" alt="create a group image"/>

<p> Private messages</p>
<img src="private_messages_home.png" alt="private messages on home image"/>