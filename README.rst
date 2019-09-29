======================
Notes on PyCon UK 2019
======================

`PyCon UK 2019`_ was held in Cardiff from Friday 13th to Tuesday 17th
September (that last day being sprints, which I did not attend this year).

This was the fourth year in Cardiff City Hall.

It was, as normal, a very good conference, and I think the committee has done
an amazing job producing it. Videos for most talks (if not all) should be up
on youtube at https://www.youtube.com/channel/UChA9XP_feY1-1oSy2L7acog. I
recommend going there and browsing. I'd recommend watching the videos for all
the talks I mention below, but of course I didn't see all of the conference!

For each talk mentioned below, I give a link to the corresponding video
(they're all up already!), and a link to slides/notes where I had it - mostly
because the speaker posted the link on the conference slack. I don't promise
to have seen/noticed all of those.

*Note:* Last year's conference felt a little weighted towards talks suitable
for beginners (mind you, that's the first year I've felt that). I think the
balance this year was a lot better.

The schedule_ was created using pretalx_, which is written by Sunday's keynote
speaker. The current version of pretalx doesn't support a phone-friendly
schedule, nor does it allow an attendee to highlight program items, but the
giggity_ app knows how to the output from pretalx, and turned out to be rather good.

*Note* Although Arm is no longer paying me as a Python programmer, they did
agree to fund me for my attendance at this conference, for which I am
grateful.

.. _`PyCon UK 2019`: https://2019.pyconuk.org/
.. _schedule: https://pretalx.com/pyconuk-2019/schedule/
.. _pretalx: https://pretalx.com/p/about/
.. _giggity: https://play.google.com/store/apps/details?id=net.gaast.giggity

For some reason I'd never actually gotten round to visiting Brodies, the
iconic coffee shop near the City Hall (see their twitter feed at
https://twitter.com/BrodiesCoffee). They make *very* nice coffee, and are also
an excellent excuse to get out into the open air during the conference.

------------------------------------------------------------------------------

Friday
======

As usual, we started with Daniele Procida's introduction to the conference,
https://www.youtube.com/watch?v=UczxyQMhkhY

*Dr Tania Allard* - Reproducible Science: The Good, The Bad, The Ugly and The Untold
------------------------------------------------------------------------------------

*Keynote* https://www.youtube.com/watch?v=XOJ_0cwpuw4

https://speakerdeck.com/trallard/reproducible-science-the-good-the-bad-the-ugly-and-the-untold

I don't have any particular notes on this, which means you should just find
the video.

*Ben Nuttall* - Astro Pi: Python on the International Space Station
-------------------------------------------------------------------

https://www.youtube.com/watch?v=xAry28g1N-0

Ben talking about the Astro Pi competitions, and how they work. I imagine this
covers some of the same material that Ben will have used as the introduction
to his CamPUG workshop (https://www.meetup.com/CamPUG/events/262369899/),
which I couldn't get to. Worth watching for an overview of the project.

*David MacIver* - You are in a maze of twisty passages
------------------------------------------------------

https://www.youtube.com/watch?v=zlHck7X4F20

David explaining an interesting algorithm, that is actually not normally of
direct use (because there's usually something obviously more efficient). That
doesn't mean it's not worth knowing about, though, and it was still a very
nice talk, with good use of visual to explain things. It left me with a
curious urge to want to implement the algorithm.

Not Python specific, worth watching.

*Alex Chan* - Sans I/O Programming
----------------------------------

https://www.youtube.com/watch?v=qwTWqy0uPbY

https://alexwlchan.net/2019/09/slides-for-pycon-uk-2019/

A nice explanation of why separating out the I/O layer from the "business
logic" (i.e., the bit that does the real work) can lead to good benefits,
including better generalisability, easier testing and other things.

Whilst the examples are in Python, the concept is not Python specific, and is
a good one. It was also interesting to see similar ideas reflected in other
items.

Other notes:

* A useful thing to put on a title slide:

    If you can't see this PLEASE MOVE FORWARD

  where the first words are the size of most of your text, and the last words
  are big enough people will *definitely* be able to see them - so if they
  can't read the beginning of the text, they just see "PLEASE MOVE FOWARD".

* Mention of https://github.com/pyslackers/slack-sansio, a "Python (a)sync
  Slack API library", which feels like it might be useful some time.

*Emanuil Tolev* - Awesome live API docs for under-resourced teams
-----------------------------------------------------------------

https://www.youtube.com/watch?v=vCp8nDgRQOA

Particularly, using live API introspection - i.e., the documentation page for
the API gives examples and allows you to try them.

He mentioned:

* https://reqres.in/, which provides "mocking your API as a service" - not a
  use case I'd considered, and interesting to look at.
* NASA - if you've got no time available, at least give good examples, and
  also this one is live
* Digital Ocean provide documentation with examples of usage alongside
* Strip also provide documentation with examples (and example results)

Providing examples alongside your documentation is a lot of work, but very
valuable to users.

He also mentioned swagger-js (https://github.com/swagger-api/swagger-js) and
specifically swagger-ui (https://github.com/swagger-api/swagger-ui).

Worth rewatching.

*Richard Terry* - Syntactic Sugar vs maintainability
----------------------------------------------------

https://www.youtube.com/watch?v=QXkHDLauOlo

http://radiac.net/pycon2019/

How to tread the line between complex code that hides irrelevancies from
users, and code that is too clever for its own good.

This was a very good talk.

metaclasses - basically just invisible decorators for your classes.

He gave django-tagulous_ (his own library) as an example, of everything you
should, and should not, do.

Basically he's trying to make the common case very easy, with enought tests to
guaranteee that it isn't going to fall over, because if it does the tracebacks
are going to be incomprehensible.

...swapping the class of an instantiated object...

As an example that clearly goes too far: another of his libraries,
python-perl_, which implements Perl regex support in Python:

.. code:: python

    $ pip install perl
    $ python
    >>> import perl
    >>> value = "Hello there"
    >>> if value =~ /^hello (.+?)$/i:
    ...     print("Found greeting:", $1)
    ...
    Found greeting: there
    >>> value =~ s/there/world/
    >>> print(value)
    Hello world

Not meant for use in production!

.. _django-tagulous: http://radiac.net/projects/django-tagulous/
.. _python-perl: http://radiac.net/projects/python-perl/)

*Samathy Barratt* - Regexplained - Understanding the theory of Regular Expressions
----------------------------------------------------------------------------------

https://www.youtube.com/watch?v=D1vEJ5X13u8

http://github.com/samathy/regexplained

Samathy explained the automata that underly regular expressions, with maths
(although luckily she explained the maths). I think this was a good
explanation, and is worth watching if you want to understand why your regular
expressions do what they do.

Note that this talk is not Python specific.

Lightning talks
---------------

https://www.youtube.com/watch?v=-uakKQQuw6k

The lightning talks are *always* worth watching.

Presented and organised this year, as last, by Mark (judy2k) Smith. With
tractor jokes.

I don't promise this list is accurate:

* Gail Ollis: max credibility -> fake beard (and "``max``" not ``min``)
* Daniel Pope: playing with numpy and images. Introducing his new numpy-based
  opengl game library: https://github.com/lordmauve/wasabi2d
* Noel: ASMR for devs
* Fero Hajnovic: Python for good in the Office for National Statistics
* Alex Chan: A robot stole my job! (prospects) - using auto-release mechanisms
  for *everything*
* David MacIver: How to have great conversations (or meetings) - see also
  http://www.liberatingstructures.com/ and http://bit.ly/DRMacIverTickTalk
  (which dereferences as https://github.com/DRMacIver/systems/blob/master/tempo.md).
* Cheuk Ting-ho: Running an open source project is like running a startup
* Rob Bricheno: Fantastic bots and where to find them - PiWars and piwarbots,
  https://piwars.org/
* Gil Goncalves: Rolling dice with Python, https://github.com/LuRsT/dragn
* How to do your job well

Board games and manual technology evening
=========================================

Most evenings PyCon UK organises something to do at the City Hall. Friday's
event was games and manual technology.

This year I played games, rather than trying to learn crochet.

The table I was at attempted to play The Mind (see
https://gameguythinks.com/the-mind-card-game/ and
https://www.boardgamegeek.com/boardgame/244992/mind). It was ... interesting.
But fun.

Then we played `In a Bind`_ (now marketed as Yogi_, "with waterproof cards"!)
and `Kitty Cataclysm`_, both by Bez_, and both of which I had taken along.

We didn't get to play `Before I kill you, Mister Spy...`_, but it was
leant out for someone else to play. Maybe next year.

.. _`In a Bind`: https://www.kickstarter.com/projects/bybez/in-a-bind
.. _Yogi: http://yogi-thegame.com/en/home/
.. _`Kitty Cataclysm`:
   https://www.kickstarter.com/projects/bybez/kitty-cataclysm-chaos-cardplay-dickery-and-cat-pun
.. _Bez: http://www.stuffbybez.com/
.. _`Before I kill you, Mister Spy...`: https://cheapass.com/before-i-kill-you-mister-spy/

Things I regret missing
-----------------------

Apparently the workshop Demystifying Neural Networks (Michal Grochmal) started
with maths, and then worked up to doing simple ML using just numpy. While I'm
not at all sure I'd have *understood* the maths, I agree that this sounds like
an interestingly different way to go at the issue, rather than just showing
how to use the available libraries.

Unfortunately, workshops don't get videoed, but the the Jupyter notebooks for
the workshop are at https://github.com/grochmal/nnag

(I shall try to mention things I *know* I would like to have seen, but of
course I shall be missing things that I didn't know would have been
worthwhile. Unfortunatley, that's the sign of a good conference.)

------------------------------------------------------------------------------

Saturday
========

*Marlene Mhangami* - Leadership and Identity in the Pan-African Python movement
-------------------------------------------------------------------------------

*Keynote* https://www.youtube.com/watch?v=c5sTa4x2o1Y

A very interesting talk by Marelene Mhangami, from Zimbabwe, who was chair of
PyCon Africa, which took place in August in Ghana.

I took a few notes to references:

* Evan Czaplicki: The Hard Parts of Open Source (a strangeloop talk by the
  creator of Elm) https://www.youtube.com/watch?v=o_4EX4dPppA
* Leaders as weavers - warp and weft, a good leader can combine these to form
  a garment. This is a metaphor from the later works of Plato, specifically
  "The Statesmen".
* Sharing (conference) tickets - buying a ticket for someone who otherwise
  would not be able to attend. This is something PyCon Africa let people do.248G

*Chloe Parkes* - Depression in the Workspace: Let's talk
--------------------------------------------------------

https://www.youtube.com/watch?v=hBvRPoSbZsg

Chloe, who is one of the conference organisers, talked about her own
experiences. As such I shan't try to summarise, but suggest you should watch
the video.

Chloe did mention the "be kind today" campaign - I found https://bekindtoday.me/

*David Sim* - One weird trick for improving your communication
--------------------------------------------------------------

https://www.youtube.com/watch?v=kCZUs41SWCQ

This was a good talk, and interesting at a meta-level because I knew some of
what he was suggesting, but hadn't thought to apply it widely enough. In
drastic summary: consider what you want the person to do as a result of your
communication.

Also, a well structured talk.

*Alex Chan* - The curb-cut effect
---------------------------------

https://www.youtube.com/watch?v=-9tqCtf3T9k

https://alexwlchan.net/2019/01/monki-gras-the-curb-cut-effect/

This slot was meant to be a talk entitled "Extracting tabular data from PDFs",
but the speaker didn't turn up. A couple of alternative talks were proposed
(by Alex and Q, who just happened to have a talk or two to hand) and the
audience voted. I'd have been happy with any of the choices, actually, but
will never grumble at a chance to see a new talk by Alex.

The example of (one story of) the origin of "curb cuts", lowered curbs for
wheelchair users and people who can't do steps, was given, along with the
benefits that this had for people who were not from the original target
population.

Basically, making things better for (e.g.) disabled people can end up making
things better for everybody. Which means that designing from scratch with
disabled people in mind will often be better for everybody.

Or, more generally "making something better for people who are excluded or
marginalised can make it better for everyone."

*Tom Easterbrook* - Dev on Wheels: The Ultimate Computer Game
-------------------------------------------------------------

https://www.youtube.com/watch?v=981j5Bu4Sek

Tom, who is in a powered wheelchair, gave a talk last year on how technology
could make it easier for disabled people at university, and thus also make
life better for everyone (`A rising tide lifts all ships`_).

This year he reported back on how he managed his degree as a whole. The audio
and slides on the video are OK, but it doesn't show Tom himself.

.. _`A rising tide lifts all ships`: https://www.youtube.com/watch?v=TyQTCEGrui4

*Rebecca Vickery* - The Fastest Way to Learn Data Science
---------------------------------------------------------

https://www.youtube.com/watch?v=b2NBZYiWf2w

The first half of the talk was about how to organise becoming (for instance) a
data scientist. The importance of setting goals, but goals that are relevant
to what you want to do. The learn -> build -> explain loop (which sounds
reminiscent of the doctor's learning method, "see one, do one, teach one").

She recommends DataQuest (https://www.dataquest.io/) as a part of this.

I thought this was a realistic and well presented approach.

*Young coders* - Showcase
-------------------------

The kids from the Young Coders workshops got to present what they had been
doing. As always, it is amazing what they get done in the time, and also how
much they manage to discover the essence of programming.

UKPA AGM
--------

https://www.youtube.com/watch?v=J3S3Ng9xNN4

This must have set a record for getting everything done, formally, in the
least amount of time possible.

Lightning Talks
---------------

https://www.youtube.com/watch?v=wi-7YIFm3Vo

Still worth watching. Still with tractor jokes.

* Connor Shearwood: We are not going to space today - an abridged history of
  (some mistakes and funny incidents in) space exploration
* Amber Wright: learning CLI through your browser,
  https://www.katacoda.com/amblina/ and
  https://github.com/amblina/katacoda-scenarios. "safe environments for
  learning something scary".
* Becky Smith: Programming in loops: knitting, and its parallels to
  programming. "If you want to teach, learn".
* Rachel Taylor: To flush or not to flush: what not to put down the toilet.
* Sam: How to make use of ``__getattr__`` to make your modules more
  interesting.
* Luis Ferro: Are you a software developer?
* Kirk Northrop: :sea: :gull: :fly: - the chances of a seagull pooing on you
  during PyCon. Beautifully done pseudo-statistics.
* Darren: What I learned from Bob. The presented plays bass for Mungo Jerry
  (Ray) in his spare time, and this was a story about another member of the
  band and why he was late for gigs,
* Jenny Potts: Coding with security in mind
* Sean Sabbage: Are you choking? or are you serious? - another of Sean's
  series of lightning talks at PyCon UK on first aid.

Conference Dinner
-----------------

I did go to the conference dinner, and as normal I enjoyed it.

I don't have a note of everyone at the table, but I know there were Ben
Nuttall, Daniel Pope, RAob Bricheno, David Spademan and Luke Spademan.

David Spademan is a prison chaplain, who always explains that he comes to
PyCon UK to keep his son, Luke, company, but he's definitely a part of the
community now, and the AGM brought him on to the board of trustees. Also, he
introduced me to more than one person from Cambridge who I didn't know!

Oh, and somehow our table won the quiz!

Things I regret missing
-----------------------

I also wanted to see

* Solveiga Vivian-Griffiths and Natalie Jakoimis on "Data Scientist Career
  Path: How to find your way throught the data science maze", because it
  sounded like it would be interesting. However, it clashed with "Dev on
  Wheels", and I wanted to see Tome Easterbrook present again.

* the aforementioned Luke Spademan on "Writing Beautiful Code: An overview of
  PEP 8". It might sound like I should know everything in a talk like this,
  but it's often worth going over territory you think you know, and it's not
  unusual to discover something you did not in fact know, or had not thought
  of. https://www.youtube.com/watch?v=5zrlZGyEwMM

------------------------------------------------------------------------------

Sunday
======

*Cheuk Ting-ho* - Do we have a diversity problem in Python community?
---------------------------------------------------------------------

*Keynote* https://www.youtube.com/watch?v=g68eJwauOww

https://slides.com/cheukting_ho/do-we-have-a-diversity-problem-in-python-community

This was a repeat of a keynote from PyLondinium (by the way, I like the fact
that several items were repeats from that conference, as I think the audience
didn't overlap an enormouse amount, and it's very nice as a speaker to be able
to re-use a talk, and refine it). I felt that the talk was a bit smoother in
this second version.

*Dom Weldon* - Dash: Interactive Visualization Web Apps with no Javascript
--------------------------------------------------------------------------

https://www.youtube.com/watch?v=L7xYBZ8JatE

Dom Weldon works at decisionLab, who use mathematical models to build tools
to help businesses. They use Dash for Proof of Concept tasks.

Dash is Python wrapped around React, allowing you to do interactive data
visualisation without needing to know javascript.

The talk gave a quick introduction to Dash, and then went over their
experience of using it, including what it was good for, and when not to use it.

The basic idea is that a data scientist should be able to take the lead
writing a prototype web app, without needing to involve someone who
understands how to write the front end in javascript.

The examples for the talk are on github, https://github.com/DomWeldon

This is an interesting complement to the approaches described by Shaun
Taylor-Morgan in his later talk.

*Martin O'Hanlon* - Blue Dot - it's a bluetooth dot
---------------------------------------------------

https://www.youtube.com/watch?v=hmDAqvoDlp0

I must admit I mostly went to this talk because it came before the next two
talks in the Ferrier Hall that I wanted to see, but I've very glad I did, as
it was a nicely done introduction to the Blue Dot application, particularly in
its explanation in the trade-offs that were made (for instance, why they don't
provide an iOS app at this stage).

See https://bluedot.readthedocs.io/en/latest/ and
https://github.com/martinohanlon/BlueDot for BlueDot itself, and there's a
useful API within that (btcomm_) for sending and receiving data over
bluetooth.

.. _btcomm: https://bluedot.readthedocs.io/en/latest/btcommapi.html


*Yeray Diaz Diaz* - Import as an anti-pattern - Demystifying Dependency Injection in modern Python
--------------------------------------------------------------------------------------------------

https://www.youtube.com/watch?v=qkGxy4c64Jg

https://speakerdeck.com/yeray/import-as-an-antipattern-demystifying-dependency-injection-in-python

This was a very nicely done talk. It's also interesting how Alex Chan's talk
on sans I/O programming addresses a subset of the concerns of this talk.

Also, and especially, it is a useful reference to the computer science names
for various concepts that we deal with in our work - starting with "dependency
injection" itself.

Rererences, all of which look very well worth following up:

* `Dependency Injection`_ by Dhanji R. Prasanna, published by Manning, and
  available to read free.
* `95 Bottles of OOP`_ by Sandi Metz and Katrina Owen. The examples are given
  in Ruby (which I for one find interesting! - Sandi Metz is well known as a
  good writer in the Ruby world, and in particula her book "Practical
  Object-Oriented Design" is very good).
* Boundaries_, a talk by Gary Bernhardt "about using simple values (as opposed
  to complex objects) not just for holding data, but also as the boundaries
  between components and subsystems."

.. _`Dependency Injection`: https://www.manning.com/books/dependency-injection
.. _`95 Bottles of OOP`: https://www.sandimetz.com/99bottles
.. _Boundaries: https://www.destroyallsoftware.com/talks/boundaries

*Tobis Kohn* - Here's Your Mistake...
-------------------------------------

https://www.youtube.com/watch?v=7gMOaWdzDSw

Ths was another very nice talk.

The speaker is a Research Associate at Cambridge University, but his
background is in teaching children to program, particularly in Python. This
led him to consider what syntax errors new programmers commonly make, and how
to improve the error messages that they get. However, his argument is also
that some of the "syntax errors" are actually a lack of understanding of the
concepts, and those also need fixing.

That's a terrible summary of a very clear talk, which I recommend watching.

The tool he refers to is TigerJython - see http://www.jython.tobiaskohn.ch/

*Gil Goncalves* - So you want to be a manager
---------------------------------------------

https://www.youtube.com/watch?v=5SyZSvSpax8

Well, no, I don't, but I know people who are *becoming* managers, and I wanted
to learn what I could maybe do to support them. And this was a very good
presentation, which I feel anyone who wants to be a manager, *and* anyone who
knows someone who wants to be a managed, should watch.

Recommended reading:

* `The Manager's Path`_ by Camille Fournier, which Gil says everyone should read
* "Managing Humans" by Michael Lopp - humorous stories about managing people 

.. _`The Manager's Path`: https://www.oreilly.com/library/view/the-managers-path/9781491973882/
  
*Konark Modi* - What do travel, food & health websites have in common? Auditing websites & apps for privacy leaks
-----------------------------------------------------------------------------------------------------------------

https://www.youtube.com/watch?v=oGb8dM-K0AU

An interesting talk. I made notes of some links (probably not all those
given):

* https://whotracks.me/
* https://mitmproxy.org/
* LocalSherriff_ is a browser extension that works out what information about
  you is being leaked/shared. It uses mitmproxy.

.. _LocalSherriff: https://github.com/cliqz-oss/local-sheriff

There are related articles by Konark Modi at https://medium.com/@konarkmodi


Lightning Talks
---------------

https://www.youtube.com/watch?v=y_lLsAEsf2A

As ever, watch the lightning talks.

* Shaun Taylor-Morgan: How growing vegetables makes me a better programmer: on
  the benefits of having an allotment.

Things I regret missing
-----------------------

I wish I'd gotten to the "Python on Hardware" community showcase.

I was very tempted by Hannah Hazi's "Don't Cross the Streams: An Introduction
to Virtual Environments" - it's another of the sort of talk that's always
useful, even if it might be covering topics that you think you already know
all about. And Hannah is a good speaker/explainer. I seem to have meant to go
to the "Benefits of Competition Based Libraries for Beginners in Python", and
not quite got to that either. https://www.youtube.com/watch?v=T-zaepH-lHc

I definitely wanted to go to Thomas Kluyver's "What does PEP 517 mean for
packaging?", as it's an important part of the progress that Python is trying to
make in its packaging story. The "Dash" talk just won out, and it wil be
interesting to watch the video for this to see if I made the right choice.
https://www.youtube.com/watch?v=s5lJsFzv_iI and
https://www.slideshare.net/takluyver/python-packaging-how-did-we-get-here-and-where-are-we-going

Since I don't have any notes between the keynote and the "Dash" talk, I think
I must have been talking to people - that's always a good choice!

I sort-of regret not going to the Code Dojo, because I've not been to a London
style code dojo before, and because people who did go reported it as great
fun. But I was definitely beginning to lag by this point, and it was nice just
to go out to dinner somewhere away from the conference.

(The repository with what people did in the dojo is at https://github.com/PyconUK/dojo19.)

------------------------------------------------------------------------------

Monday
======

*Tobias Kunze* - while history: continue
----------------------------------------

*Keynote* https://www.youtube.com/watch?v=Cup-GHdKJvQ

This was wonderful, not least because the slides were beautiful, and the font
was wonderfully appropriate.

The history presented was interesting, and well explained, but also acted as a
reflection on the Python 2 to 3 transition!

NB: in passing, I should mention the blog "Going Medieval",
https://going-medieval.com/, which gets particularly irritated at use of the
term "The Dark Ages" to mean a time of ignorance and stagnation. Specifically,
see
https://going-medieval.com/2017/05/26/theres-no-such-thing-as-the-dark-ages-but-ok/


*Hannah Hazi* - Telling Stories with Python and Ren'Py
------------------------------------------------------

This was the workshop that Hannah "practiced" at the September CamPUG meeting,
and which I missed. So I rather wanted to go to it, especially as I actually
had an idea for something to do that might fit the mechanism.

It was great fun, and I now need to find some pictures to illustate the
"interactive pamphlet" (So you think you might have Divine Right To Be King)
which I made.

Two groups actually managed to make complete stories, with illustrations: one
on how to pet a cat (all the pictures of the same cat!), and one on how to get
to the conference from the railways station (including getting lost near the
castle). Both of those were very effective.

Hannah's write up is at https://raspberrycheesecake.github.io/renpy.html

*Vishnu Anirudh* - Managing Big Data in Machine Learning projects
-----------------------------------------------------------------

https://www.youtube.com/watch?v=4XpHk85_x0E1G

The speaker works for oxbotica, an autonomous vehicle startup. They have to
deal with 4TB/car/day of compressed data.

The talk was about https://dvc.org/, data version control, a VCS for ML
projects. Since it is domain specific, it also handles the organisation of the
project, and can manage/run pipelines as well.

Stores data "in the cloud".

*Shaun Taylor-Morgan* - Python in the Browser
---------------------------------------------

https://www.youtube.com/watch?v=QiqiPeXVKQg

Shaun is an ex-colleague who now works for Anvil_. He talked about 6
more-or-less representative examples of Python in the Browser that have some
maturity/stability.

This was the talk I'd hoped for from the title and abstract - a good overview
of the field. And an interesting contrast to the talk on Dash earlier in the
conference.

(Anvil use, and contribute to, Skulpt_, which was one of the solutions
discussed.)

.. _Anvil: https://anvil.works/
.. _Skulpt: http://skulpt.org/

I wrote down a reference to http://hourofpython.trinket.io, as showing
examples of doing Python (in the browser) - this seems to be another use of Skulpt.

*Richard Izzo* - Hangar; git for your data
------------------------------------------

https://www.youtube.com/watch?v=t35wB-R6mr4

This solution is aimed at *numerical* data rather than textual - i.e., big
data, etc.. But not specifically machine learning.

* efficiently store n-dimensional arrays
* time travel history
* integrity of data and history
* zero cost branch/merge
* distribution and collaboration
* *partial* clone/fetch small parts of massive datasets
* able to saturate request at various scales
* simple to use

Separate out the types of data, and don't try to treat them all the same. If
you need to retrieve the book-keeping part of the information, you don't need
to retrieve the actual (very large) data itself.

I *think* it sounded like you need to give up direct access to the big data -
in other words, allow hangar to have complete control of it. That's not
necessarily a bad thing.
  
They're still working on adding backend storage mechanisms, but have a
good/useful subset so far.

There's an API, inspired by git, but looks decent. NB: humans are not the main
consumers of data.

The fundamental ideas did sound well thought out, as he present it.

https://github.com/tensorwerk/hangar-py

(I thought to myself that Hangar feels a bit like it is doing for big data
what Calibre does for ebooks - but that might be a poor analogy.)

Lightning Talks
---------------

Before the lightning talks, there were some announcements:

* Remember to tell people there's a creche each year, and it's free
* Daniele stepping down as conference directory, next year will be Kristian
  Glass.
  
And a nice quote from Daniele "I like to think of myself as sinister but honest"

On to the lightning talks.

https://www.youtube.com/watch?v=d1vJjM9Kn7A

Apologies if I missed anything, or got names wrong.

* Thomas Kluyver: (borg backup) content addressable
  storage. https://www.borgbackup.org/. Looks interesting.
* Little Anonymous: Python mailing system: https://pyuubin.io/
* Turn on SSL and verify certs
* John Chandler: Everything I've learnt from Russell Winder talks, in 5
  minutes (A tribute). Very nice if you know Russell, who wasn't at the
  conference this year.
* Maraina: Songs from last night: a practical guide to GDPR data access
  requests. A group of friends were playing music using spotify, and did not
  have a record of the playlist. They were able to make a GDPR request to get
  it (re)constructed for them. See also https://gooddatamovement.org/
* Mike Grochmal: Does correlatio lie to us?
* Alex: Turning the UK off and on again (inspired by actual lightning)
* Python Turkey: Istanbul, April 2020, http://tr.pycon.org/
* Daniele and Marlene: Report on PyCon Africa 2019, https://africa.pycon.org/report/
* Glen: Escape Rooms with some Python
* Jan Freyberg: Collaborating with your model in Python
* Domninic Oram: The climate crisis and one not-so-easy thing you can do about
  it. https://climatestrike.org/, extinction/rebellion https://rebellion.earth/
* Emma and friends: live flappy bird! Pygame, microbits and crocheted gloves
* Andrew Bennett: From panic to presenting
* David: Fractals and numpy: printing to draw julia sets

And we were then led in dancing by Chloe in her cowboy/horse costume, and the
(non-sprint part of the) conference came to its end: https://www.youtube.com/watch?v=ackJTE8ZTqM


Things I regret missing
-----------------------

I will watch the video of Nikoleta Glynati's "The Fallacy of Meritocracy",
which was well reported. She gave a very interesting keynote last year, so I
expect it to be good. However, I'd missed Hannah's workshop at CamPUG, so that
won out. https://www.youtube.com/watch?v=aYSVceNyJ201g

I didn't really consider going to Daniele Procida's "The worlds' cheapest,
simplest plotter" (and it clashed with the workshop), but the reports of it
were good (heh, any Daniele talk is likely to be good), so I shall watch it on
video. https://www.youtube.com/watch?v=u4Jh1daCl60. There's also
https://brachiograph.readthedocs.io/ and https://github.com/evildmp/BrachioGraph

I would also quite like to have seen Carlo Pereira Atencio's talk on "An
Introduction to Hardware Drived in (Micro)Python". https://www.youtube.com/watch?v=0HQ-zPbuWg4

And I'm sure Shaun Taylor-Morgan did a good job with his Anvil workshop, but I
can make him give that at CamPUG some time, and I already know I need to play
with Anvil.

------------------------------------------------------------------------------

Tuesday
=======

Given the choice of going home late Monday evening and taking Tuesday off to
recover, or doing a little tourism in the morning on Tuesday and getting home
at a more sensible time, I chose the latter. So in the morning I got up
slightly later, checked out of my hotel, and explored Cardiff Castle, which
I've seen from the outside, but never from the inside. I recommend it (it was
worth the £13.50 entry fee). I also got to see a bit more of Cardiff City
Centre, and to eat lunch at `The Stable`_, which I've been to twice before. I
had a very nice cider, and the Rad Kimchi pizza (pulled pork, roasted peppers,
kimchi, and edible flowers) which was both interesting and something I'd order
again.

.. _`The Stable`: https://cardiff.stablepizza.com/

Just for interest, I note that Alex Chan put the planned sprints up on the
conference slack:

* Pretalx with Tobias/Owen – the tool used to choose talks and create the conference schedule
* TickTalk with David – drop-in structured conversations, based on a Friday lightning talk
* Music workshop with Sandy – musical knowledge useful but not required
* Packaging with Thomas – help to get your code up on PyPI
* Brachiograph for Daniele – creating a tiny plotter using Python and cheap household materials
* Come to PyCon Africa with Daniele/Vince – half an hour of conversation after lunch about what it’s like to attend and African PyCon
* Volunteer at PyCon UK – similar conversation for PyCon UK
* Cables and capture sprint – treasure hunt time! Find all the cables around the venue, bring them back to the Assembly Hall. Also: help improve the software used to upload videos to YouTube.
* Trans Code in Room I – creating tools that are helpful for the LGBTQUIAP+ community. Allies welcome.
* Wasabi 2D with Daniel – game framework for education purposes, writing simple games + flushing out bugs
* Raspberry Pi things with Ben – including gpiozero (library used to interact with GPIO pins) and piwheels (building ARM Python packages for RPi users)
* A starter motor for students with Gail – creating resources for university students
* Command-line tools with Gil – mini-workshop on CLI tools like the Git command-line. Half an hour or so.
* PyPy with Ronan – implementing new features for Python 3.7 in PyPy with one of the core devs
* Neural network research with Michal
* Getting a new project up on GitHub with Andrew
* Some stuff with Django and tourism (sorry, I didn’t catch the name)
* Sprinting on Django itself with Ian
* Django app for matching free world penpals with incarcerated LGBTQ+/HIV positive people with Dawn
* Command-line program to automate something for a university supervisor

That may or may not be the same as what happened, of course.

Oh, and other future conferences:

* EuroSciPy 2020, Bilbao, 27-21 July
* PyCon Italia 2020, Florence, 2-5 April
* PyCon Lithuania 2020, Vilnius, 23-25 May
* PyCon NA 2020, Windhoek, 18-20 February


------------------------------------------------------------------------------

CamPUG meetup
=============

The October meeting of the Cambridge Python User Group (CamPUG, Tuesday 1st
October, https://www.meetup.com/CamPUG/events/265064979/) will be partly a
retrospective on PyCon UK; those of us who attended can compare notes, and
those who did not can learn why they would like to have been there.

--------

  |cc-attr-sharealike|

  These notes and any related files are released under a `Creative Commons
  Attribution-ShareAlike 4.0 International License`_.

.. |cc-attr-sharealike| image:: images/cc-attribution-sharealike-88x31.png
   :alt: CC-Attribution-ShareAlike image

.. _`Creative Commons Attribution-ShareAlike 4.0 International License`: http://creativecommons.org/licenses/by-sa/4.0/
