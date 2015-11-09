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

## Scripts

`camera.sh` takes the photo.
```bash
#!/bin/bash

raspistill -q 95 -tl 2000 -t 0 -rot 270 -o images/image%06d.jpg
```

## Time-lapse video

Create time-lapse video from images.

      $ brew install ffmpeg
      $ cd images
      $ ffmpeg -framerate 30 -i image%046.jpg -c:v libx264 -r 30 outputfile.mp4

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

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/hackerspacepp/raspbian-time-lapse. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

