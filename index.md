---
layout: workshop      # DON'T CHANGE THIS.
root: .               # DON'T CHANGE THIS EITHER.  (THANK YOU.)
country: "us"      # lowercase two-letter ISO country code such as "fr" fr(see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
humandate: "June 10-11, 2019"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 6:00 pm (lunch time to match the conference)"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-06-10      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-06-11        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Elizabeth Wickes, Sher! Hurt"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: []     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
contact: ["amiller@northwestern.edu", "sheraaron@carpentries.org"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
etherpad: https://pad.carpentries.org/2019-06-10-ttt-LSSTC            # optional: URL for the workshop Etherpad if there is one
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
locations:
   venue: "Carnegie Mellon University"
   address: "LSSTC @ Carnegie Mellon Unviersity"
   latlng: ","
---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->

<!--
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
-->
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->

<p>
  The course is aimed at everyone who is
  interested in becoming a better teacher. In particular, this training
  is aimed at those who want to become <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.lc_site }}">Library Carpentry</a>, and <a href="{{ site.dc_site }}">Data Carpentry</a>
  Instructors, run workshops and contribute to The Carpentries training
  materials. You don't currently have to be an instructor or a
  teacher to attend this workshop, but you do need to be willing and
  committed to becoming one and to improving your teaching techniques.
</p>

<p>
  <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.dc_site }}">Data Carpentry</a>, and 
  <a href="{{ site.lc_site }}">Library Carpentry</a>'s mission is to
  help scientists, researchers, and librarians get more research done in less time
  and with less pain by teaching them basic lab skills for scientific
  computing.  This hands-on two-day workshop covers the basics of
  educational psychology and instructional design, and looks at how to
  use these ideas in both intensive workshops and regular classes.
</p>
<p>
  The workshop is a mix of lectures and hands-on lessons where you
  practice giving a short lesson using approaches learned and
  implement some of the teaching techniques which we will discuss.
  This is training for teaching, not technical training; you do not
  need any particular technical background, and we will not be
  teaching that. This workshop is based on the constantly revised and
  updated
 <a href="{{ site.training_site }}">curriculum</a>.
</p>

<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
  -->
<h3 id="where">Where</h3>

{% assign inperson = "false" %}
{% for loc in page.locations %}

{% capture online %}{{ loc.venue | downcase }}{% endcapture %}

<h4>{{ loc.venue }}</h4>

{% if online == "online" %}

This is an online event. We will meet using the online videoconference software Zoom. You will need to <a href="https://zoom.us/download">download and install their client</a> to connect with your instructors. The link to use for this event is <{{ loc.address }}>.

{% else %}
{% assign inperson = "true" %}
{{ loc.address }} {% if loc.latlng %} Get directions with
    <a href="//www.openstreetmap.org/?mlat={{loc.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
    or
    <a href="//maps.google.com/maps?q={{loc.latlng}}">Google Maps</a>. {% endif %}

{% endif %}
{% endfor %}

{% if inperson == "true" %}

<h4 id="accessibility">Accessibility</h4>

We are committed to making this workshop
accessible to everybody.
The workshop organisers have checked that:

<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>

Materials will be provided in advance of the workshop and
large-print handouts are available if needed by notifying the
organizers in advance.  If we can help making learning easier for
you (e.g. sign-language interpreters, lactation facilities) please
please get in touch (using contact details below) and we will
attempt to provide them.

{% endif %}

<h3>Requirements</h3>

Participants should bring a laptop that is Internet connected and has a
functioning browser. If you have it, a device for recording audio and video
(mobile phones and laptops are OK) is useful as throughout the two days, we
are going to record one another teaching in pairs or threes. It does not have
to be high-quality, but it should be good enough that you can understand what
someone is saying.

Please note that after this course is over, you will be asked to do
three short follow-up exercises online in order to finish qualifying
as an instructor: the details are available at
<a href="{{ site.training_site }}/checkout/">{{ site.training_site }}/checkout/</a>.
If you have any questions about the workshop, the reading material,
or anything else, please get in touch.


<h3>Code of Conduct</h3>

All participants are required to abide by The Carpentries <a href="{{
site.swc_site }}/conduct/">Code of Conduct</a>.



<h3 id="contact">Contact</h3>
<p>
Please email
{% if page.contact %}
  {% for contact in page.contact %}
    {% if forloop.last and page.contact.size > 1 %}
      or
    {% else %}
      {% unless forloop.first %}
      ,
      {% endunless %}
    {% endif %}
    <a href='mailto:{{contact}}'>{{contact}}</a>
  {% endfor %}
{% else %}
  to-be-announced
{% endif %}
for more information.
</p>

<hr/>

<h2 id="preparation" name="preparation">Preparation</h2>

<p>
  Please read the following before the workshop begins:
</p>
<ol>
  <li><a href="{{ site.training_site }}/papers/science-of-learning-2015.pdf">The Science of Learning</a></li>
</ol>
<p>
  Please also read through <em>one</em> episode of one of The Carpentries lessons below   
  carefully, so that you can do some exercises based on it on the
  first day of the class.  An episode is one page of a lesson.
</p>

  <ul>
  <li><a href="{{ site.swc_site }}/lessons">Software Carpentry Lessons</a></li>
  <li><a href="{{ site.dc_site }}/lessons">Data Carpentry Lessons</a></li>
  <li><a href="{{ site.lc_site }}/lessons">Library Carpentry Lessons</a></li>
  </ul>
  

<hr/>

<h2 id="materials" name="materials">Training Materials and Schedule</h2>

<p>
  Please see <a href="{{ site.training_site }}">this site</a> for course material and tentative schedule. Please note that the schedule on the linked page is for a general training. Your instructors will be working to align this workshop's schedule with the larger conference schedule. Please refer to your instructors, class announcements, and etherpad for more information when it is available.
</p>


<hr/>

<!--

<div class="row">
  <div class="col-md-6">
    <h3>Day 1</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Welcome </td> </tr>
      <tr> <td>09:15</td> <td>How Learning Works: The Importance of Practice </td> </tr>
      <tr> <td>10:20</td> <td>How Learning Works: Expertise and Instruction </td> </tr>
      <tr> <td>11:10</td> <td>Morning Coffee </td> </tr>
      <tr> <td>11:25</td> <td>How Learning Works: Working Memory and Cognitive Load </td> </tr>
      <tr> <td>12:15</td> <td>Building Teaching Skill: Getting Feedback </td> </tr>
      <tr> <td>12:35</td> <td>Lunch </td> </tr>
      <tr> <td>13:35</td> <td>Creating a Positive Learning Environment: Motivation and Demotivation </td> </tr>
      <tr> <td>14:40</td> <td>Creating a Positive Learning Environment: Mindset </td> </tr>
      <tr> <td>15:20</td> <td>Afternoon Coffee </td> </tr>
      <tr> <td>15:35</td> <td>Building Teaching Skill: The Importance of Practice </td> </tr>
      <tr> <td>16:45</td> <td>Wrap-Up and Homework for Tomorrow </td> </tr>
      <tr> <td>17:05</td> <td>Finish </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Day 2</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Welcome Back </td> </tr>
      <tr> <td>09:10</td> <td>Building Teaching Skill: Lesson Study </td> </tr>
      <tr> <td>10:05</td> <td>Building Teaching Skill: Live Coding </td> </tr>
      <tr> <td>11:05</td> <td>Morning Coffee </td> </tr>
      <tr> <td>11:20</td> <td>Building Teaching Skill: Performance Revised </td> </tr>
      <tr> <td>12:00</td> <td>Lunch </td> </tr>
      <tr> <td>13:00</td> <td>The Carpentries: Workshop Introductions </td> </tr>
      <tr> <td>14:10</td> <td>The Carpentries: How We Operate </td> </tr>
      <tr> <td>15:15</td> <td>Afternoon Coffee </td> </tr>
      <tr> <td>15:30</td> <td>The Carpentries: Teaching Practices </td> </tr>
      <tr> <td>16:00</td> <td>Afternoon Wrap-Up </td> </tr>
      <tr> <td>16:45</td> <td>Finish </td> </tr>
    </table>
  </div>
</div>

-->

<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}
<hr/>

<p id="etherpad">
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
  <br/>
  We will use this Etherpad for chatting, taking notes, and sharing URLs and bits of code.
</p>

{% endif %}

<h2 id="pre_workshop_survey">Surveys</h2>

<p>
  Before attending the workshop, please fill out <a href="{{ site.instructor_pre_survey }}{{ site.github.project_title }}">our pre-training survey</a>.
</p>


<p>
  After the workshop, please fill out <a href="https://carpentries.github.io/instructor-training/06-feedback/#surveys">our post-assessment survey</a>.
</p>
