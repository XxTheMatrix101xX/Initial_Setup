This tool was created to make transition as smooth as possible for windows users.
Tool creates a backup of C:\Users\%USERNAME%\AppData\Roaming\Korecoin\wallet.dat
Initial setup of "updating" wallets only need -zapwallettxes however this exe 
also makes a backup of the wallet.dat and moves the tor and onion folders over 
to the new directory so that you can keep your hostname, this also makes the 
initial wallet connect to peers faster because it needs to do less setup.

Tool:
Prompts user asking if they have the old dev's wallet on their system.
 - If no: 
    + Creates self destruct file and starts new wallet regularly before 
        destroying itself.
 - If yes:
    + Checks to see if old dev's wallet is running.
      - if yes;
          + Prompts user to shut down the wallet then waits for the wallet to shut down.
          + Continues.
      - if no;
        + Continues.
        + Displays current task.
        + Creates self destruct file.
        + Creates root folder and then moves \Onion\, \Tor\, and wallet.dat to root.
        + Creates backup wallet.dat folder and copies original to that folder.
        + Runs Wallet with -zapwallettxes variable.
        + Runs self destruct file.
      
      
      
Tested Environments:
64x Windows 10 Professional
  - Runs flawlessly
64x Windows 10 Home
  - Runs flawlessly
64x Windows 7 Professional
  - Runs correctly however on self destruct wallet is shut down.
      + Added extra time before self destruct so all required files could be made.
