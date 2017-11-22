# email images

Links were extracted from the emails using regular expressions. 
Since most of the links are tracking links added by the email service, I used python requests to check their status and find the URL that they resolve to. 
For example `http://uidaho.us6.list-manage.com/track/click?u=e8b26a2bfdf3335ca7d0c9eef&id=4647df556e&e=55d7947efc` was embedded in the email source, which resolves to `http://www.socialmobilityindex.org/`.
The tracking links were then replaced by their actual urls, since the tracking links are likely to go away.

Many tracking links are broken and resolve to a uidaho 404 message. The uidaho 404 message is unfortunate because it returns a 200 status and also obscures the original request.
The original request can be reconstructed by looking at the `404.aspx` query. 
For example, `http://www.uidaho.edu/404.aspx?item=%2fed%2fabout%2feducation-building-renovation-project&user=extranet%5cAnonymous&site=website` can be reconstructed by deleting "/404.aspx?item=", replacing the escaped entity "%2f" with "/", and removing the additional parameters after "&". Thus, `http://www.uidaho.edu/ed/about/education-building-renovation-project` was the original request, that can be used at Archive.org. 
Add the date of the email to the archive.org url api, `http://web.archive.org/web/` + `[date in 1-24 digits only]` + `/` + `[the orginal url including protocol]`. 
For example, `http://web.archive.org/web/2015/http://www.uidaho.edu/ed/about/education-building-renovation-project` will retrieve the broken link from the web archive.
