---
layout: page
title: Home
---
{% assign items = site.data.fridayletters %}

<link href="{{ site.baseurl }}/css/vanilla-dataTables.min.css" rel="stylesheet" type="text/css">

## Browse The Friday Letter Archive

The Friday Letter is the University of Idaho's long-running, weekly message from the president to internal and external members of the university community.
The University of Idaho Library captures items from the Office of the President's web page on an annual basis.
The archive currently contains more than 80 items ranging from 2015 to 2017.

This table provides sorting and basic search of the archive contents. 
Click on the "Read" link to see the full message.

<table id="letter-table" class="display">
    <thead>
        <tr>
            <th>Date</th>
            <th>Subject</th>
            <th>Body</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}        
        <tr>
            <td>{{ item.date }}</td>
            <td>{{ item.title }}</td>
            <td>{{ item.body | strip_html | truncatewords: 40 }} <a href="{{ site.baseurl }}/letters/{{ item.date }}.html">Read</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>

<script src="{{ site.baseurl }}/css/vanilla-dataTables.min.js" type="text/javascript"></script>

<script>
    var dataTable = new DataTable("#letter-table", {
        perPage: 20,
    });
</script>
