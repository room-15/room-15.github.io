# Android Room Rules Template

This repo is used to hold the pre-built content for the [Stack Overflow Android chat room][room15]'s rules. To build the rules, you'll need a version of Ruby and the [kramdown] gem installed. You may optionally substitute kramdown for any multimarkdown utility that's compatible with its extensions by setting and exporting the MULTIMARKDOWN environment variable.

Once you've got kramdown or something equivalent, run the `build` script and the index.html will be popped out.

Currently, the built rules are hosted at <http://spifftastic.net/room.15/>.

For quick reference:

- head.in — this contains the top third of the output HTML, including the inline stylesheet and such.
- tail.in — the bottom third. Just closes off the remaining tags opened by the head.
- body.md — the rules text itself. Contains the revision number at the top. Each time a new version of the rules is published, this number should be incremented. Minor fixes don't merit revision increments.

[room15]: http://chat.stackoverflow.com/rooms/15/android
[kramdown]: http://kramdown.gettalong.org
