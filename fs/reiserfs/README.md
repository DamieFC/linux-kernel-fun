# LICENSING

ReiserFS is hereby licensed under the GNU General
Public License version 2.
<br>
Source code files that contain the phrase "licensing governed by
reiserfs/README" are "governed files" throughout this file.  Governed
files are licensed under the GPL.  The portions of them owned by Hans
Reiser, or authorized to be licensed by him, have been in the past,
and likely will be in the future, licensed to other parties under
other licenses.  If you add your code to governed files, and don't
want it to be owned by Hans Reiser, put your copyright label on that
code so the poor blight and his customers can keep things straight.
All portions of governed files not labeled otherwise are owned by Hans
Reiser, and by adding your code to it, widely distributing it to
others or sending us a patch, and leaving the sentence in stating that
licensing is governed by the statement in this file, you accept this.
It will be a kindness if you identify whether Hans Reiser is allowed
to license code labeled as owned by you on your behalf other than
under the GPL, because he wants to know if it is okay to do so and put
a check in the mail to you (for non-trivial improvements) when he
makes his next sale.  He makes no guarantees as to the amount if any,
though he feels motivated to motivate contributors, and you can surely
discuss this with him before or after contributing.  You have the
right to decline to allow him to license your code contribution other
than under the GPL.
<br>
Further licensing options are available for commercial and/or other
interests directly from Hans Reiser: hans@reiser.to.  If you interpret
the GPL as not allowing those additional licensing options, you read
it wrongly, and Richard Stallman agrees with me, when carefully read
you can see that those restrictions on additional terms do not apply
to the owner of the copyright, and my interpretation of this shall
govern for this license.
<br>
Finally, nothing in this license shall be interpreted to allow you to
fail to fairly credit me, or to remove my credits, without my
permission, unless you are an end user not redistributing to others.
If you have doubts about how to properly do that, or about what is
fair, ask.  (Last I spoke with him Richard was contemplating how best
to address the fair crediting issue in the next GPL version.)
<br>
# END LICENSING

Reiserfs is a file system based on balanced tree algorithms, which is
described at https://reiser4.wiki.kernel.org/index.php/Main_Page 
<br>
Stop reading here.  Go there, then return.
<br>
Send bug reports to yura@namesys.botik.ru.
<br>
mkreiserfs and other utilities are in reiserfs/utils, or wherever your
Linux provider put them.  There is some disagreement about how useful
it is for users to get their fsck and mkreiserfs out of sync with the
version of reiserfs that is in their kernel, with many important
distributors wanting them out of sync.:-) Please try to remember to
recompile and reinstall fsck and mkreiserfs with every update of
reiserfs, this is a common source of confusion.  Note that some of the
utilities cannot be compiled without accessing the balancing code
which is in the kernel code, and relocating the utilities may require
you to specify where that code can be found.
<br>
Yes, if you update your reiserfs kernel module you do have to
recompile your kernel, most of the time.  The errors you get will be
quite cryptic if your forget to do so.
<br>
Real users, as opposed to folks who want to hack and then understand
what went wrong, will want REISERFS_CHECK off.
<br>
Hideous Commercial Pitch: Spread your development costs across other OS
vendors.  Select from the best in the world, not the best in your
building, by buying from third party OS component suppliers.  Leverage
the software component development power of the internet.  Be the most
aggressive in taking advantage of the commercial possibilities of
decentralized internet development, and add value through your branded
integration that you sell as an operating system.  Let your competitors
be the ones to compete against the entire internet by themselves.  Be
hip, get with the new economic trend, before your competitors do.  Send
email to hans@reiser.to.
<br>
To understand the code, after reading the website, start reading the
code by reading reiserfs_fs.h first.
<br>
Hans Reiser was the project initiator, primary architect, source of all
funding for the first 5.5 years, and one of the programmers.  He owns
the copyright.
<br>
Vladimir Saveljev was one of the programmers, and he worked long hours
writing the cleanest code.  He always made the effort to be the best he
could be, and to make his code the best that it could be.  What resulted
was quite remarkable. I don't think that money can ever motivate someone
to work the way he did, he is one of the most selfless men I know.
<br>
Yura helps with benchmarking, coding hashes, and block pre-allocation
code.
<br>
Anatoly Pinchuk is a former member of our team who worked closely with
Vladimir throughout the project's development.  He wrote a quite
substantial portion of the total code.  He realized that there was a
space problem with packing tails of files for files larger than a node
that start on a node aligned boundary (there are reasons to want to node
align files), and he invented and implemented indirect items and
unformatted nodes as the solution.
<br>
Konstantin Shvachko, with the help of the Russian version of a VC,
tried to put me in a position where I was forced into giving control
of the project to him.  (Fortunately, as the person paying the money
for all salaries from my dayjob I owned all copyrights, and you can't
really force takeovers of sole proprietorships.)  This was something
curious, because he never really understood the value of our project,
why we should do what we do, or why innovation was possible in
general, but he was sure that he ought to be controlling it.  Every
innovation had to be forced past him while he was with us.  He added
two years to the time required to complete reiserfs, and was a net
loss for me.  Mikhail Gilula was a brilliant innovator who also left
in a destructive way that erased the value of his contributions, and
that he was shown much generosity just makes it more painful.
<br>
Grigory Zaigralin was an extremely effective system administrator for
our group.
<br>
Igor Krasheninnikov was wonderful at hardware procurement, repair, and
network installation.
<br>
Jeremy Fitzhardinge wrote the teahash.c code, and he gives credit to a
textbook he got the algorithm from in the code.  Note that his analysis
of how we could use the hashing code in making 32 bit NFS cookies work
was probably more important than the actual algorithm.  Colin Plumb also
contributed to it.
<br>
Chris Mason dived right into our code, and in just a few months produced
the journaling code that dramatically increased the value of ReiserFS.
He is just an amazing programmer.
<br>
Igor Zagorovsky is writing much of the new item handler and extent code
for our next major release.
<br>
Alexander Zarochentcev (sometimes known as zam, or sasha), wrote the
resizer, and is hard at work on implementing allocate on flush.  SGI
implemented allocate on flush before us for XFS, and generously took
the time to convince me we should do it also.  They are great people,
and a great company.
<br>
Yuri Shevchuk and Nikita Danilov are doing squid cache optimization.
<br>
Vitaly Fertman is doing fsck.
<br>
Jeff Mahoney, of SuSE, contributed a few cleanup fixes, most notably
the endian safe patches which allow ReiserFS to run on any platform
supported by the Linux kernel.
<br>
SuSE, IntegratedLinux.com, Ecila, MP3.com, bigstorage.com, and the
Alpha PC Company made it possible for me to not have a day job
anymore, and to dramatically increase our staffing.  Ecila funded
hypertext feature development, MP3.com funded journaling, SuSE funded
core development, IntegratedLinux.com funded squid web cache
appliances, bigstorage.com funded HSM, and the alpha PC company funded
the alpha port.  Many of these tasks were helped by sponsors other
than the ones just named.  SuSE has helped in much more than just
funding....

