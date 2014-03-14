## Overview

This repository contains the source for the slides that appear in this
video:

<a href='https://vimeo.com/jedcn/reveal-ck-stop-haml-time'>
  <img alt="Video Thumbnail" width="306" height="178" src='https://raw2.github.com/jedcn/reveal-ck/gh-pages/images/reveal-ck-stop-haml-time-thumbnail.png' />
</a>

## Building

This repository only contains the source of the presentation. If you
wanted to view it, you'd have to build it-- and the repository does
contain a [Rakefile][Rakefile] that has instructions to do just that.

If you wanted to build the presentation on your machine, you'd type:

```
bundle
rake
```

And then you'd open a browser to the resulting html:

```
open slides/index.html
```

Or you could start up the built-in webserver and look at that:

```
reveal-ck serve
open http://localhost:10000
```

## Resources

These slides are built with [reveal-ck][reveal-ck].

[reveal-ck][reveal-ck] lets you author slides in Markdown, Textile,
Haml, or Slim. These particular slides were created with Haml.

If you have questions about reveal-ck, check out the
[reveal-ck wiki][reveal-ck-wiki].

If you have questions about haml, check out http://haml.info/.

[reveal-ck]: https://github.com/jedcn/reveal-ck
[reveal-ck-wiki]: https://github.com/jedcn/reveal-ck/wiki
[Rakefile]: ./Rakefile
