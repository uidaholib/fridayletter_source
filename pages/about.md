---
title: About
layout: page
permalink: /about.html
# add image to index page bootstrap jumbotron
featured-image:
---

<div class="row" markdown="1">
<div class="col-md-8" markdown="1">

# About The Friday Letter Archive

For over two decades, [The Friday Letter](https://www.uidaho.edu/president/communications/friday-letter) has been the University of Idaho's weekly message from the President to internal and external members of the university community. 
The [Office of the President's website](https://www.uidaho.edu/president/communications) publishes a variety of official communications including the Friday Letter, Vandal Connection, reports, videos, and presentations.
To ensure continued access to this unique content, University of Idaho Library captures items in their original web context on an annual basis.
Select materials are made available in our digital collections.

The Friday Letter Archive archive currently contains hundreds items dating back to 2013.
These items are in a variety of formats, including emails, slides, videos, speech transcripts, reports, and links to external articles.
To browse the collection, a [table]({{ '/' | relative_url }}) provides sorting and basic search. 
Alternatively, the content can be discovered using the [Search page]({{ '/search/' | relative_url }}) or [Google Custom Search]({{ '/search/google-search.html' | relative_url }}).

For current news, please visit [Office of the President Communications](http://www.uidaho.edu/president/communications).

*Thank you to Brian Keenan for help assembling this content 2017 - 2019.*

</div>
<div class="col-md-4" markdown="1">
<img src="{{ '/images/fridayletter-header.jpg' | prepend: site.objects }}" class="img-fluid my-3">
<div class="alert alert-warning" role="alert">
<em>Please note</em>, the archived email messages are in a variety of formats and may not display as originally intended. Some images, links, and functionality may be broken or out of date. If you would like to recover a broken link, please try pasting the URL in the <a href="https://archive.org/web/" target="_blank" rel="noopener">Internet Archive Wayback Machine</a>.
</div>
</div>

<div class="col-md-8" markdown="1">

## About Communications 

This collection includes materials harvested from the [Office of the President Communications](http://www.uidaho.edu/president/communications) website, including The Friday Letter, Vandal Connection, In the News, Videos, Presentations, and Letters and Reports.

- **The Friday Letter** is U of I's long-running, weekly message straight from the president to members of the Vandal family. Each week during the academic year, and with breaks for holidays, the president offers an update on Vandal teaching and learning, research and scholarship, and notable initiatives and priorities. Alumni and friends are welcome to join students, faculty and staff in receiving the newsletter.
- **The Vandal Connection** is a quarterly digital newsletter directly from the president. Intended for people with a strong interest in the work of the university, the newsletter provides timely updates on progress toward goals, work on important initiatives, and the performance of critical programs. The Vandal Connection newsletter is issued twice in the fall academic semester and twice in the spring academic semester.
- **In the News** represents a selection of guest columns and articles involving the president.
- **Letters and Reports** represent significant presidential letters, progress reports and other announcements shared with the campus.

## Technical Notes 

Since many of the emails were sent out using a campaign newsletter service, links included in the body of the message are obscured by tracking service links.
These types of links are temporary, likely to become broken, and will not be traceable in the future.
To avoid this issue, links were extracted from the emails using <a href="https://en.wikipedia.org/wiki/Regular_expression"  target="_blank" rel="noopener">regular expressions</a> or <a href="https://www.crummy.com/software/BeautifulSoup/"  target="_blank" rel="noopener">Beautiful Soup</a> (if html). 

When ingesting new emails, links are checked using Python to find their status and the actual URL that they resolve to. 
For example `http://uidaho.us6.list-manage.com/track/click?u=e8b26a2bfdf3335ca7d0c9eef&id=4647df556e&e=55d7947efc` was embedded in the email source, which resolves to `http://www.socialmobilityindex.org/`.
The tracking links are then replaced by their actual URLs.

To see the page as it was when originally linked, it is possible to try using the <a href="https://archive.org/web/" target="_blank" rel="noopener">Internet Archive Wayback Machine</a> to retrieve the resource.
Add the date of the email to the Wayback API following this pattern: 

`https://web.archive.org/web/` + `[date in 1-24 digits only]` + `/` + `[the original url including protocol]` 

For example, `https://web.archive.org/web/2015/http://www.uidaho.edu/ed/about/education-building-renovation-project` will retrieve the broken link from the web archive.
If the Wayback has the page archived, it will resolve to the capture nearest the date you requested.

Some links to internal U of I pages are also broken. 
U of I's servers will return a 404 page that also obscures the original link.
By looking at the 404 URL, the original request can be reconstructed by deleting `/404.aspx?item=`, replacing the escaped entity `%2f` with `/`, and removing any additional parameters after `&`. 
Once reconstructed, the original URL can be used in the Wayback Machine.

For example, for the 404 URL: 

`https://www.uidaho.edu/404.aspx?item=%2fed%2fabout%2feducation-building-renovation-project&user=extranet%5cAnonymous&site=website`

The original request was: 

`https://www.uidaho.edu/ed/about/education-building-renovation-project` 

Which can then be used in the Wayback Machine to retrieve the original page as it was in 2015:

`https://web.archive.org/web/2015*/https://www.uidaho.edu/ed/about/education-building-renovation-project`

</div>
</div>