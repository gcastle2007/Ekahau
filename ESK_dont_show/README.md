Есть ответ от Support, которые помогает решить данную проблему:

Please open the control panel and browse to network connection. You should have there Sidekick (NDIS-6 device) that is seen as an ethernet connection. Right click on that and choose "status" and then on the first page "details", this should give you the ip address. 

Other option is to open Command prompt with run as admin command and type ipconfig / all , and provide me the output.

Open notepad or other text editor of your choice with run as command. 
Choose file open, 
Browse to c:\Program files\Ekahau\Ekahau Pro\bin

open Ekahau Pro.lap file and locate the following

-Desp.host=10.60.35.50:40003 @ 10.60.35.51

And edit this to:
-Desp.host=10.60.35.50:40003

Save the file (please make sure that when saving choose "all the files" in the file selection filter not to save the file by accident to .txt file. 

Open Ekahau Pro HDPI.lap

open Ekahau Pro.lap file and locate the following

-Desp.host=10.60.35.50:40003 @ 10.60.35.51

And edit this to:
-Desp.host=10.60.35.50:40003

Save the file (please make sure that when saving choose "all the files" in the file selection filter not to save the file by accident to .txt file. 

Close the editor

start Ekahau Pro
