<p align="center">
  <a href="http://turtlerover.com" alt="Turtle Rover"><img src="https://avatars3.githubusercontent.com/u/36553642?s=84&v=4" alt="Turtle Rover" /></a>
</p>
<h1 align="center">Firmware: Shield</h1>
<h4 align="center">This is software for microprocessor on <a href="https://github.com/TurtleRover/electronics-shield">electronics-shield</a></h4>

<p align="center">
  <a href="https://travis-ci.org/TurtleRover/firmware-shield">
    <img src="https://travis-ci.org/TurtleRover/firmware-shield.svg?branch=master" alt="Build Status">
  </a>
  <a href="https://github.com/TurtleRover/firmware-shield/releases">
    <img src="https://img.shields.io/github/release/TurtleRover/firmware-shield.svg" alt="Release"></a>
  <a href="https://github.com/TurtleRover/firmware-shield/blob/master/LICENSE">
      <img src="https://img.shields.io/github/license/TurtleRover/firmware-shield.svg">
  </a>
  <a href="https://twitter.com/TurtleRover">
    <img src="https://img.shields.io/twitter/follow/TurtleRover.svg?style=social&label=Follow">
  </a>
</p>
<p align="center">
  <a href="http://turtlerover.com" alt="Website">Website</a> |
  <a href="https://www.facebook.com/TurtleRover/" alt="Facebook">Facebook</a> |
  <a href="https://www.youtube.com/channel/UCxukvEct3wP0S5FACa3uelA" alt="YouTube">YouTube</a>
</p>

## Data frames in HEX

| Prefix | Body | Postfix | Description |
| --- | --- | --- | --- |
| `10` | ⬆️`00` `00` `00` `00` : `7f` `7f` `7f` `7f`<br>⬇️`80808080`:`ffffffff`| `0d0a` | Motors speed set simultaneously for all wheels. The first range is for moving forward, the second - backward, accordingly. |
| `30` | `00000000` | `0d0a` | Read battery voltage |
| `84` | `(axis_1 >> 8) & 0xff` `axis_1 & 0xff` `(axis_2 >> 8) & 0xFF` `axis_2 & 0xff` | `0d0a` | Set manipulator orientation (only axis without gripper)	- 2 bytes MSB first |
| `94` | | `0d0a` | Set gripper value |


## Dependencies:

 * adding repository 
```
$ [sudo] add-apt-repository ppa:team-gcc-arm-embedded/ppa
```

```
$ sudo apt-get update 
```
 * installing toolchain
 
```
$ sudo apt-get install gcc-arm-embedded
```

## Compiling & building

```
  $ make
```
