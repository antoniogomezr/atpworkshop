Start using Swingbench
Change to the “bin” subdirectory where swingbench is installed. In this example: its:

/home/opc/Downloads/swingbench/bin

And start swingbench by issuing the command below (see screenshot and explanation of parameters below) (make sure to use your wallet and ATP database user/password information, fields that need to be modified to your values are in black). Notice the command below will create a database user name “soe” (-u soe with a password “Atpxweek2018” (-p Atpxweek2018) which will be used by Swingbench to load data and run workloads.

./oewizard	-cf -cs	/home/opc/Downloads/wallet_atpxweek.zip -cs atpxweek_tpurgent -ts	DATA -dbap adminuserpassw -dba admin -u soe -p Atpxweek2020_# -async_off -scale .5 -hashpart 
-create -cl -v	-debug

Understanding the parameters above

•	-cf speficies the location of the wallet file
•	-cs specifies the ATP service to connect to
•	-ts name of the table space to install swingbench into. For ATP it is always DATA
•	-dba user admin created during ATP instance creation
•	-dbap admin user password
•	-u new database user created for swingbench data
•	-p new user (above) password
•	-async_off async commits are not supported in ATP
•	-scale in GB’s, data size, plus additional 50% of data for indexes
•	-debug will display back each step of the process – leave this out if too much data is on your screen

Creation time will vary depending on where you are running it from and may take 20 minutes or more. Once complete verify the tables created correctly by running the following command :

./sbutil -soe \
-cf /c/wallets/wallet_atpxweek.zip \
-cs atpxweek_tpurgent \
-u soe \
-p Atpxweek2020_# \
-val



