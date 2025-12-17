Download and Install Mudlet: https://www.mudlet.org/download/46/
Delete all of the profiles in there under profiles: C:\Users\youruser\\.config\mudlet\profiles\
Create a new Profile named Torilmud
server: torilmud.org
port: 9999
navigate to options, put in username and password
check connect auomatically

@@ Download This: https://github.com/Nyyrazzilyss/NyyLIB/archive/refs/heads/master.zip
extract and copy

copy this: C:\Users\youruser\\.config\mudlet\profiles\Torilmud\NyyLIB-master.zip\NyyLIB-master\
to
C:\Users\youruser\\.config\mudlet\profiles\Torilmud\
EVERYTHING

launch mudlet in offline mode
@set reconnect 1 or to whatever number u wanna focus on

use package manager to load:NyyLIB013dev.mpackage with package manager
this will be in the directory you copied.

open scripts and find the appropriate script, noted here with a .txt file,
but the function name is right, just replace the code.

@map alias https://github.com/zenevan/SAS/blob/main/map.txt -- updates maps
init files: https://github.com/zenevan/SAS/blob/main/initNyyLIB.txt  --fixes rescue and wizards
train config: https://github.com/zenevan/SAS/blob/main/setupTrain%20config.txt -- adds trains
sqldb update https://github.com/zenevan/SAS/blob/main/sqlfunctions.txt
data for sql lookup drop in root of your profile

right click these and save in root: C:\Users\youruser\\.config\mudlet\profiles\Torilmud\

short: https://github.com/zenevan/SAS/blob/main/short_stats.txt
long: https://github.com/zenevan/SAS/blob/main/long_stats.txt

@map updateok

lua loadItemDatabase()

connect to mud, enjoy
