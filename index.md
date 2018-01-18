---
layout: page
title: Home
---
{% assign items = site.data.fridayletters %}

<link href="{{ site.baseurl }}/css/vanilla-dataTables.min.css" rel="stylesheet" type="text/css">

<img src="images/fridayletter-header-crop.jpg" style="width:100%">

## Browse the Friday Letter Archive

The Friday Letter is the University of Idaho's long-running, weekly message from the president to the university community. The University of Idaho Library captures items from the [Office of the President's web page](https://www.uidaho.edu/president) on an annual basis and select materials are made available in the [Web Archive Collections](https://www.lib.uidaho.edu/digital/webarchive/).
For more information, please contact [Special Collections and Archives](https://www.lib.uidaho.edu/special-collections/contactus.html).

<!--<style>
#columns {
    display: flex;
    align-items: center;
    justify-content: space-around;
    flex-grow: 1;
    margin: 0;
}
</style>-->
<table id="letter-table" class="display">
    <thead>
        <tr>
            <th>Title</th>
            <th>Date</th>
            <th>Body</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}        
        <tr>
            <td><a href="{{ site.baseurl }}/letters/{{ item.date }}.html">{% if item.title %}{{ item.title }}{% else %}{{ item.date | date: "%a, %b %d, %Y" }}{% endif %}</a></td>
            <td>{{ item.date | replace: "-", "/" }}</td>
            <td>{{ item.body | strip_html | truncatewords: 40 }} <a href="{{ site.baseurl }}/letters/{{ item.date }}.html">Read</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>

<script src="{{ "/css/vanilla-dataTables.min.js" | absolute_url }}" type="text/javascript"></script>

<script>
    var dataTable = new DataTable("#letter-table", {
        perPage: 20,
        fixedColumns: true,
        layout: {
            top: "{info}{search}",
            bottom: "{select}{pager}"
        },
        columns: [
            { select: 1, sort: "asc" }
        ]
    });
</script>
