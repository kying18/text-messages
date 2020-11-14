# text-messages

Send your friends AUTOMATED text messages as a little prank :P
Inspired by the Bee Movie texts viral tik tok

Note: this script will only work if you have a Mac

In `send.scpt` you'll find an applescript that tells your laptop to send a message through iMessage:
```
on run {targetPhoneNumber, targetMessageToSend}
    tell application "Messages"
        set targetService to 1st service whose service type = iMessage
        set targetBuddy to buddy targetPhoneNumber of targetService
        set targetMessage to targetMessageToSend
        send targetMessage to targetBuddy
    end tell
end run
```

Then, we call this through `main.py` like so:
```
os.system('osascript send.scpt {} "{}"'.format(phone_number, message))
```

This line basically tells your computer to run the applescript we defined with the given phone number and message.
So we can send one word at a time if we just create a for loop and run this line a gazillion times, where the
message each time is that single word :)
