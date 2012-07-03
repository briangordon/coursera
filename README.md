Coursera Downloader
===================
[Coursera] is creating some fantastic, free educational classes (e.g., algorithms, machine learning, natural language processing, SaaS).  This script allows one to batch download lecture videos for a Coursera class.  Given a class name, it scrapes the course listing page to get the week and class names, and then downloads the video lectures into appropriately named files and directories.

Rather than downloading resources from the class page (which requires an active enrollment and a session cookie), this fork downloads the lecture videos from the course preview section. This 
means that you can download all lectures from classes you missed, but you won't be able to get lecture notes or the other resources.

Currently it only downloads the mp4 version of each lecture; I may add an argument for selecting the webm version in the future.

Directions
----------

Requires Python 2.x (where x >= 5) and a free Coursera account enrolled in the class of interest.

1. Install any missing dependencies.

  * [Beautiful Soup 3]  
  Ubuntu/Debian: `sudo apt-get install python-beautifulsoup`  
  Other: `easy_install BeautifulSoup`  
  * [Argparse] (Not necessary if Python version >= 2.7)  
  Ubuntu/Debian: `sudo apt-get install python-argparse`  
  Other: `easy_install argparse`  
  * [easy_install] (for the above)  
  Ubuntu: `sudo apt-get install python-setuptools`  
  
2. Create a Coursera.org account and enroll in a class.
e.g. http://saas-class.org  

3. Login to that class with your web browser.

4. Locate or export your Netscape-style cookies file with a browser extension.  
    Chrome: [Cookie.txt Export]  
    Firefox: [Export Cookies 1.2]  
      
5. Run the script to download the materials.  
    General:                 `coursera-dl saas`  
    Filter by section name:  `coursera-dl saas -sf "Chapter_Four"`  
    Filter by lecture name:  `coursera-dl saas -lf "3.1_"`  
    Download only ppt files: `coursera-dl saas -f "ppt"`

NB: I recommend using the argument `-w wget` (if wget is in your PATH) so that it uses wget to download videos.


Troubleshooting
---------------

* If it's finding 0 sections, you most likely have an invalid cookies file.
  * It's possible the cookies are already expired. This can happen very quickly.
    Try recreating your cookies.txt by logging in and re-copying the cookie file (step 3-5 above).  
  * If you get the error: "ValueError: need more than 1 value to unpack", the
    process or text editor you used to copy the cookie.txt probably converted the
    tabs to spaces.

* If you've tried recreating your cookies.txt and still have problems, please post to [issues].


Contact
-------
Post bugs and enhancement requests to [issues].  Send any other questions or comments to:  
John Lehmann: first last at geemail dotcom or [@jplehmann]  

  

[@jplehmann]: www.twitter.com/jplehmann
[Cookie.txt Export]: https://chrome.google.com/webstore/detail/lopabhfecdfhgogdbojmaicoicjekelh
[youtube-dl]: http://rg3.github.com/youtube-dl
[Coursera]: http://www.coursera.org
[Beautiful Soup 3]: http://www.crummy.com/software/BeautifulSoup
[Argparse]: http://pypi.python.org/pypi/argparse
[wget]: http://sourceforge.net/projects/gnuwin32/files/wget/1.11.4-1/wget-1.11.4-1-setup.exe
[Export Cookies 1.2]: https://addons.mozilla.org/en-US/firefox/addon/export-cookies
[easy_install]: http://pypi.python.org/pypi/setuptools
[issues]: https://github.com/jplehmann/coursera/issues
