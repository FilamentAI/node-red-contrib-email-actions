# node-red-contrib-email-actions
=========================

A simple Node-RED (http://nodered.org) node to perform operations on emails retrieved via the email-in node.

# Features

* Leaves original payload unchanged
* Optionally Adds lables to emails (__GMail-only__ feature)
* Optionally moves emails to a specified folder

# Install

Run the following command in the root directory of your Node-RED install (typically ~/.node-red)

    npm install node-red-contrib-email-actions
    
# Example

<pre>
[{"id":"80db7ff2.eb058","type":"e-mail in","z":"5aed5fb2.3b8c","name":"","protocol":"IMAP","server":"imap.gmail.com","useSSL":true,"port":"993","box":"INBOX","disposition":"Read","repeat":"300","x":130,"y":100,"wires":[["20ec9cc4.044104","aabb1a97.7ca4e8"]]},{"id":"20ec9cc4.044104","type":"debug","z":"5aed5fb2.3b8c","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"true","x":310,"y":120,"wires":[]},{"id":"d6238d84.d27e9","type":"mailactions","z":"5aed5fb2.3b8c","name":"","protocol":"IMAP","server":"imap.gmail.com","useSSL":true,"port":"993","box":"INBOX","outbox":"Processed","tag":"","x":470,"y":80,"wires":[["ac43a21c.be1df"]]},{"id":"ac43a21c.be1df","type":"debug","z":"5aed5fb2.3b8c","name":"after actions","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"true","x":650,"y":80,"wires":[]},{"id":"aabb1a97.7ca4e8","type":"function","z":"5aed5fb2.3b8c","name":"","func":"msg.email = { \n    \"folder\" : \"Testing\",\n    \"label\" : \"my label\"\n}\nreturn msg;","outputs":1,"noerr":0,"x":310,"y":80,"wires":[["d6238d84.d27e9"]]}]
</pre>
  
# Author

Andy Feltham, https://github.com/FilamentAI
