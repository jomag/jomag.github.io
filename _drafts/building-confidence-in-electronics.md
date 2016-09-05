

Some ten years ago today I started my first stumbling steps into electronics
on a somewhat professional level. I have no extensive schooling on the subject
and I'm still by no means an expert but I can get by in most situations or at
least know where to look for help.

The problem with me and electronics was from the start, and to some extent still
today, that I could just not really get my head around the subject. I had a solid
understanding of software development and had no problem understanding the internals
of microcontrollers and other digital devices, but once outside that domain I was
lost.

I'm totally convinced about a relation with what you *think* you can and learn
and what you really *can* learn. If you lack confidence in yourself you will
have a very hard time getting good at the given subject, whatever that may be, because
you will doubt that you have a good enough understanding on each detail you learn
so that the big picture will never be clear.

So today I have two tips to anyone coming from the same background as me: a
solid understanding of computers and software development, and a wish to get into
electronics.

### 1. There's a sharp divide between digital and analog electronics

This divide is almost as the divide between chemistry and physics: while
chemistry is just physics at atomic level, the two subjects are still so separate
that you can easily be competent in one of them with little knowledge about the
other.

You can transfer most electronic problems from discreet components and analog
electronics to digital: implement filters, button debouncing, timers etc in software.
Prefer components with a digital interface: temperature sensors with I2C interface
rather than thermistors and so on. Learn about logic levels on signals and how to
use an oscilloscope to debug problems.

You will of course run into some problems that are more analog in nature. Try
to solve them using the Internet to see what others have done. When you see recurring
themes, such as the use of decoupling capacitors, read up on them until you have
a reasonable understanding. When you do run into harder problems such as noisy signals,
make a bit more effort to understand why they occur.

You will get very far with this mindset. Building Arduino clones from scratch with
with a bunch of interfaces and external components will soon be no match. Once
you get to that level, here's my next advice:

### 2. There's no sharp divide between digital and analog electronics

You will soon find that even though you've focused on the digital solutions
you've stumbled upon enough electronics problems that you will be able to read
and understand 90% of most schemas. You will also be experienced enough to understand
that the last 10% is nothing to really worry about in most cases.

Electronics are easy. It's the complexity of most schemas that make it hard: there's
just too much going on. And without experience you will look upon them like a child
with no means to filter the information flow for important stuff and stuff that can
be ignored and what parts are related.
