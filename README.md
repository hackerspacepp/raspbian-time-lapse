# raspbian-time-lapse

## Linux distribution
[RASPBIAN WHEEZY](https://www.raspberrypi.org/downloads/raspbian/)

## Item list

* __Raspberry PI 2__ - Credit Card-sized single-board computer.
* __Power Supply__ - 5V 2A Ultra HQ USB Power Supply & Cable (EU)
* __Heat Sink__ - Raspberry Pi Heat Sink Kit - Black
* __Camera__ - Raspberry Pi Camera Board (5MP, 1080p, v1.3)
* __Wifi__ - WiFi Dongle - Nano USB
* __Case__ - Nwazet Pi Camera Box Bundle (Case, Lens & Wall Mount) - B+/2
* __SD Card__ - 8GB MicroSD Card
* __Lens 1__ - Magnetic Telephoto 2x Lens
* __Lens 2__ - Magnetic Wide Angle Lens
* __Lets 3__ - Fisheye Lens

## Scripts

`camera.sh` takes the photo.
```bash
#!/bin/bash

raspistill -q 15 -tl 1000 -t 0 -o images/image%06d.jpg
```

## Time-lapse video

Create time-lapse video from images.

    $ brew install ffmpeg
    $ cd images
    $ ffmpeg -framerate 30 -pattern_type glob -i '*.jpg' -c:v libx264 -r 30 outputfile.mp4

## Considerations

* Place behind window to avoid dealing with weather issues.
* Place close to window surrounded by black fabric to minimize
  reflection in window and ambient lighting.
* Avoid using tape to place camera.
* Needs software alarm to detect if camera has is face down or have been
  moved. Also check time of day.
* Focus on mornings and afternoons.
* Needs monitoring to detect if syncing has stopped or device has become
  unavailable.
* Camera should be hung from the top of the window or ceiling.

## Problems
* Need hi-quality Wifi Dongle, connectivity to file-system while
  capturing is very slow (Solved).
* Crontab not an option, resolution too low (minutes).

## Adjustable Parameters
* Exposure
* Shutter Speed
* White Balance

## TODO

* Use [Nimbius](http://cloudnimbus.org/) or
  [ownCloud](https://owncloud.org/) running on second RPi with
  external hard-drive as store.
* Create and archive time-lapse videos on backup device.
* Switch to 32GB SD-card on camera device.

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/hackerspacepp/raspbian-time-lapse. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](contributor-covenant.org) code of conduct.

## License

Copyright (c) 2015 Anders Jiras and Ole J. Rosendahl

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
