espeak-ruby
===========

espeak-ruby is a small Ruby API for utilizing [espeak](http://espeak.sourceforge.net) and [lame](http://lame.sourceforge.net/) to create Text-To-Speech mp3 files.
See the [live demo](http://rors.org/demos/espeak-ruby).

Install
-------

Add _espeak-ruby_ to Gemfile

```ruby
gem "espeak-ruby", require: "espeak"
```

Example
-------

```ruby
# Speaks "YO!"
speech = ESpeak::Speech.new("YO!")
speech.speak # invokes espeak
  
# Creates hello-de.mp3 file
speech = ESpeak::Speech.new("Hallo Welt", voice: "de")
speech.save("hello-de.mp3") # invokes espeak + lame
```

Features
--------

Currently only subset of espeak features is supported. 

```ruby
:voice => 'en'    # use voice file of this name from espeak-data/voices
:pitch => 50      # pitch adjustment, 0 to 99
:speed => 170     # speed in words per minute, 80 to 370
```

These are default values, and they can be easily overridden:

```ruby
ESpeak::Speech.new("Zdravo svete", voice: "sr", pitch: 90, speed: 200).speak
```

Requirements
------------

* <http://espeak.sourceforge.net>
* <http://lame.sourceforge.net>

Related
-------

* [espeak-http](http://github.com/dejan/espeak-http) - Micro web app for Text-To-Speech conversion via HTTP powered by Ruby, Sinatra, lame, espeak and espeak-ruby

Licence
-------

Copyright (c) 2008 Dejan Simic

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
