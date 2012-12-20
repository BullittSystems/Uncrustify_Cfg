# Uncrustify Me!
-

[Uncrustify](http://https://github.com/bengardner/uncrustify) is a handy source formatter. This repository contains the version that I use in my projects as well as my configuration file.

### Xcode integration

Integration with Xcode is a bit of a hassle these days since they removed the User Scripts functionality in Xcode 4. The current way I make this work is to create a service in Automator Service with the following content:

    /path/to/uncrustify -l OC -q -c /path/to/config file/uncrustify.cfg | cat
    echo ""
    
The service should be set to receive selected text in Xcode.app. Input is entire selection and output replaces selected text.

After the Automator Service is created, I go to the keyboard shortcuts preferences and configure a shortcut command. My shortcut of choice is \^⌥⌘/.

#####Note:
Recent research has shown that you *might* be able to do add a script as a user behavior in Xcode and get this functionality to work without needing to use Automator. Something to play with in the near future.