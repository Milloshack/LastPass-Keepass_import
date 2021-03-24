# LastPass-Keepass_import
# when you import Keepass into LastPass it creates Secure Notes instead of Passwords

I noticed this issue and from what I can see there is no fix as of today. From reading some boards and discussions it was evident that the issue was trigered by Passwords in KeePass that do not have a URL value.

The way I fixed it was to use NOtePad++ find and replace feature to edit the XML file and add **"Enter URL"** to all the passwords that did not already had a URL.

The search in Notepad++ to find the field for empty URLS is (make sure you select "Extended" in the search box mode, in the Find window):

        <Key>URL</Key>\r\n\t\t\t\t\t\t\t\t<Value />

each "\t" is a tab character, I had to do the search with eight tabs and with seven tabs, to get them all.

the replace text for the above search sould be:

        <Key>URL</Key>\r\n\t\t\t\t\t\t\t\t<Value>Enter URL</Value>

make sure you keep the same amount of tabs between the find and replace.

MillosHack
