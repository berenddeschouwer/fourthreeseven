# fourthreeseven

## Description

A Unicode code page 437 font

Use this font if you have a historic application that you would like to
view on a modern desktop.  You should use this font if you have an application
that was written for DOS, or PC-based Unix/Linux/BSD that you would like
to run on a modern unicode-based OS.

You'll know that you need this if you struggle with the following screenshot,
and wish it looked like the second screenshot.

![Alt text](doc/badfont.png?raw=true "mc using 'monospace'")

![Alt text](doc/goodfont.png?raw=true "mc using 'fourthreeseven'")

In particular this is useful for terminal (vt100 or dos) emulators in browsers.

## Using

To use this font in a browser, add the following to your CSS files:

```
  @font-face {
    font-family: 'FourThreeSeven';
    font-style: normal;
    font-weight: 400;
    src: local('FourThreeSeven'), url(FourThreeSevenMedium.ttf) format('truetype');
  }

  #mydiv {
    font-family: FourThreeSeven, monospace;
    line-height: 100%; /* prevent horizontal stripes/vertical gaps */
  }
```

## Where to Use

This has been tested on modern browsers in 2015.

This means: Firefox on Linux, Chrome on Linux, Firefox on Android, Chrome on
Android.

## Pitfalls

This implements code page 437.  The glyphs at location 0x80 to 0xFF are
different from unicode.

This font was written to be small in data, for use on tablets and phones,
and therefore all unicode glyphs above 0xFF have been deleted.

Android devices will attempt to substitute missing glyphs from the built-in
fonts.  Linux browsers will render a square to show a missing glyph.

## Further Reading

If it's your intention to use a monospace font for this kind of work, I
recommend reading up on CSS line-height, and how different browsers render
fonts.  Despite what is promised, font rendering is not pixel-exact across
browsers -- or even the same browser on different platforms.

## History

A long, long time ago applications had a need for only a few characters.
Applications assumed Latin English characters, Arabic numberals, and a few
extras.

It was deemed a good idea to standardise on some characters.  So we developed
standards.  Two of them, of course.  EBCDIC on the mainframes, and ASCII on
the PCs.

Later non-Latin characters (mainly Cyrillic) were added.  So again, we needed
a standard map, and again there were two standards.  Code page 437 on western
european and US PCs, and code page 850 on eastern european PCs.  These were
embedded in the BIOS.

Even later Unicode was developed.  Unicode -- in keeping with tradition --
also had multiple standards. but that's OK since none of them match either
code page 437 or 850.

Browsers use unicode.  Old applications assume code page 437.  This is where
they meet.

## Source

The font glyphs come from GNU Unifont, available at
http://unifoundry.com/unifont.html

## License

These font files are licensed under the GNU General Public License,
either Version 2 or (at your option) a later version, with the exception
that embedding the font in a document does not in itself constitute a
violation of the GNU GPL. The full terms of the license are in LICENSE.txt.

