# SIAM_scraper
code for scraping SIAMs conferences

To start, I want to get a link to the program for each conference, both up comming and archived. I recommend starting with the archived ones because the data shouldn't be changing on these which will make it easier to work with. Here is a link to it:
https://www.siam.org/conferences/archives

try using the python library 'request' to grab the html. Then look at the html with a text editor (its better if you get a text editor that does color coding, I recommend sublime text or something similar) and from there try writting regex to extract the names of the conferences, or better yet, a link to the program. To learn how to use requests, try putting this prompt into chatgpt:

'python script to grab the html at a given link'

It gave me working code using the url 'example.com' but you can swap that out for the siam url

Once you start looking at the HTML, you'll see that its quite repetative and formulaic. If you control-F for 'DS23' and then for 'DS21' you will find that the html code looks almost the same. You want to exploit this pattern to make the regex grab exactly what you want.

Please ask chatgpt to do as much of this as you can. This will be faster and I personally think this is still a good way to learn. This is what I did recently to learn more about regex.

Ideally I want this data: the name of the conference, the start and end dates (and start and end times). Conference address (might be empty if held online). And a link to the program. For example, I want a link to this program (ds23):

https://meetings.siam.org/program.cfm?CONFCODE=DS23

I previously thought I could just get the conference code (DS23) and put this at the end of the URL, but then this was only working for some conferences. My hope is to scrape all conferences, but this hasn't happened yet. This is the main problem I'd like you to figure out.

To figure this sort of thing out, mainly you just need to look at the data and determine how to know what the conference code is, based on the conference name, or possibly some other info that is contained in the list of archived conference.


This is all I want for a first start, then later on I want to scrape the actual conference data and put it all into a database. At first just putting it into a json file will be easier. Also I have a few recommendations. If you use the requests library to pull html files, not that you might get an error sometimes because it might have troubles reaching the server for various reasons (networks are mysterious sometimes). I recommend saving the html file with a first python script (eg: gethtml.py) then reading it into a second python program (eg: processHTML.py). This will be faster and less error prone.

If you have any questions please ask me or chatgpt.
