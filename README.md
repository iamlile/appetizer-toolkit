# appetizer-toolkit [![Build Status](https://travis-ci.org/appetizerio/appetizer-toolkit.svg?branch=master)](https://travis-ci.org/appetizerio/appetizer-toolkit) [![Windows Build](https://ci.appveyor.com/api/projects/status/github/appetizerio/appetizer-toolkit)](https://ci.appveyor.com/project/mingyuan-xia/appetizer-toolkit)
`appetizer-toolkit` is the core of [Appetizer](https://www.appetizer.io), which provides the ability to:
* record touchscreen events from one device and replay to many (aspect ratios must be the same)
* control multiple devices concurrently (e.g., run a shell command, install an app, etc.)
* mirror the touchscreen events from one device to many in real time (aspect ratios must be the same)

`appetizer-toolkit` is a command line tool, available on Windows 7+, MacOS Mavericks+ and Linux. It also comes with SDK for [Python](https://github.com/appetizerio/appetizer-toolkit-py) and [Nodejs](https://github.com/appetizerio/appetizer-toolkit-js). `appetizer-toolkit` requires `adb` to be present in `PATH`.

Please submit an issue for bugs, enhancements and feature requests. Pull requests are welcomed too.

## Installation
For Linux and MacOS, download the executable (`appetiezr-toolkit-darwin-x64` for MacOS and `appetizer-toolkit-linux-x64` for Linux); For Windows, download and unzio `appetizer-toolkit-win.zip`. You might want to add to PATH to use the tool globally.

```
usage: appetizer-toolkit-linux-x64 [-h] {version,trace,adb,devices,plan} ...

positional arguments:
  {version,trace,adb,devices,plan}
                        commands
    version             Print the version information and exit
    trace               Record and replay touchscreen events
    adb                 Control the local ADB
    devices             Command devices
    plan                Compose and execute a test plan file

optional arguments:
  -h, --help            show this help message and exit

```

## Record and Replay
To record and replay touchscreen events, use `appetizer-toolkit-* trace`:
```
usage: appetizer-toolkit-linux-x64 trace [-h] {info,replay,record} ...

positional arguments:
  {info,replay,record}  actions
    info                Get the detail of a trace file
    replay              Replay a touchscreen event trace to some devices
    record              Record a trace of touchscreen events

optional arguments:
  -h, --help            show this help message and exit
```

[![Record and replay](https://i.vimeocdn.com/video/583660790_640.jpg)](https://vimeo.com/176421640)

## Control Multiple Devices and Mirror Touchscreen Events
To work with multiple devices, use `appetizer-toolkit-* devices`:
```
usage: appetizer-toolkit-linux-x64 devices [-h]
                                           {list,screenshot,mirror,control}
                                           ...

positional arguments:
  {list,screenshot,mirror,control}
                        actions on the devices
    list                List the details of connected devices
    screenshot          Take a screenshot
    mirror              Mirror the touchscreen events from one device to many
                        in real-time
    control             Control devices

optional arguments:
  -h, --help            show this help message and exit
```

Mirror the touchscreen events from one device to many in real-time.
[![mirroring](https://i.vimeocdn.com/video/585120374_640.jpg)](https://vimeo.com/176421482)

## ADB related
`adb` from Android SDK is required for `appetizer-toolkit`. The toolkit itself can detect the existence of the adb binary and control the adb server with it.
```
usage: appetizer-toolkit-linux-x64 adb [-h]
                                       
                                       {check-server,start-server,kill-server,detectadb}
                                       ...

positional arguments:
  {check-server,start-server,kill-server,detectadb}
                        actions on the adb server
    check-server        Check the state of the adb server
    start-server        Start the adb server
    kill-server         Kill the adb server
    detectadb           Detect the path to the adb program

optional arguments:
  -h, --help            show this help message and exit
```
