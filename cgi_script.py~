#!/usr/bin/env python
import cgi
import os
import sys
import json

loggedin = False
form = cgi.FieldStorage()

if form.getvalue('user') == 'gus' and form.getvalue('password') == '12345':
	loggedin = True
if 'loggedin=true' in os.environ['HTTP_COOKIE']:
	loggedin = True

if loggedin:
	print "Set-Cookie: loggedin=true"

print "Content-type: text/html"
print
print "<HTML><BODY><H1>Hello World!</H1>"
print "<FORM method='POST'>"
print " <INPUT name='user'/>"
print " <INPUT name='password' type='password' />"
print " <BUTTON type='submit'>Log in</BUTTON>"
print "</FORM>"
print "<P>Query String: " + os.environ['QUERY_STRING'] + "</P>"
print "<P>Browser: " + os.environ['HTTP_USER_AGENT'] + "</P>"
#print "<P>Standard Input is: " + sys.stdin.read(int(os.environ['CONTENT_LENGTH'])) + "</P>"
#print "<P>"
#print "Username was " + form.getvalue('user')
#print "Password was " + form.getvalue('password')
#print "</P>"
if loggedin:
	print "Logged in ok"
	
#cgi.print_environ()
#print json.dumps(dict(os.environ), indent=4)


print "</BODY><HTML>"

