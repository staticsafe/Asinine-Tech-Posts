---
date: '2012-02-10 10:51:43'
layout: post
slug: python-development-on-windows
status: publish
title: Python development on Windows
wordpress_id: '1237'
categories:
- Programming
tags:
- development
- python
- windows
---

This post will be talking about how to set up a proper Python environment on Windows for development work.

<!-- more -->

Things that we need and where to get them:



	
  * [Python](http://python.org/getit/) (make sure to get Python 2 or 3 depending on what you are developing for)

	
  * [Pip](http://www.pip-installer.org/en/latest/installing.html)

	
  * [Cygwin](http://www.cygwin.com/) (optional, but can be helpful for the tools it comes with)

	
  * [Windows Powershell](https://en.wikipedia.org/wiki/Windows_PowerShell) (comes by default with Windows 7; you can still use cmd but I prefer Powershell due to its nice aliases. )

	
  * A text editor of your choice. (My preference is [Sublime Text 2](http://www.sublimetext.com/2))




There are a few more steps to getting this working properly.

	
  1. Firstly we add the directory Python resides in to the user PATH.
To do this, go to the Windows Control Panel -> System -> Advanced System Settings -> Advanced -> Environment Variables. Now add a user PATH variable if it doesn't already exist. We will be adding other paths here later on. My path variable:
`C:\Python27`

	
  2. To test this, open a command prompt, and type python, you will then get a python prompt[![](http://asininetech.com/a/2012-02-10-python-development-on-windows/pythonshell.png)](http://asininetech.com/a/2012-02-10-python-development-on-windows/pythonshell.png)

	
  3. Now that we have Python up and running properly, we will be installing pip which will let us install third party modules easily. Its nice to have even if you are not planning on using any third party modules. The pip installer site instructs us to use curl to get the correct installer scripts but you may not have curl/wget if you don't have Cygwin installed.

	
  4. Download the two installer scripts to your C:\Users\USERNAME directory using your browser.

	
  5. Execute the distribute_setup.py script using Python, like this:
`python distribute_setup.py`

	
  6. Then execute the get-pip script, like this:`
python get-pip.py`

	
  7. Now you have pip installed we need to make it accessible via the command prompt, to do this we add the Python Scripts directory to our path variable. So our PATH variable value now looks like this:
`C:\Python27;C:\Python27\Scripts`

	
  8. Now try pip out. `
pip install requests`

	
  9. Congrats, your Python development environment is ready.


P.S - [requests](http://docs.python-requests.org/en/latest/) > [urllib2](http://docs.python.org/library/urllib2.html) 
Example:
{% codeblock lang:python %} 
# vim: fileencoding=utf-8

import os
import requests

def main():
r = requests.get('https://github.com/staticsafe/useful-scripts/blob/master/webserversetup.py')
file_name = "webserversetup.py"
f = open(file_name, 'wb')

f.write(r.content)
f.close()
if __name__ == '__main__':
main()
{% endcodeblock %}
