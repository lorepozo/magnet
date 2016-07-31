# magnet

Search. Select. Stream.

__`magnet`__ is a command-line torrent search scraper for magnet links. It can pass a selected magnet (and additional parameters) through to [peerflix](http://github.com/mafintosh/peerflix) to start downloading (and streaming) the search result automatically. Or you could pipe the output from __`magnet`__ into your preferred torrent utility!

This utility gets search results and magnet links from [extratorrent.cc](https://extratorrent.cc).

The search isn't limited to _just_ video!
```bash
$ magnet "Ubuntu" 1 --
```

## Usage

##### Search:
```bash
$ magnet "Night of the Living Dead 1968"
1: Night Of The Living Dead 1968 720p BluRay x264 CtrlHD PublicHD
2: Night Of The Living Dead 1968 720p BRRip x264 x0r
3: Night of the Living Dead 1968 BDRip hV
4: Night Of The Living Dead 1968 1080p Bluray x264 hV N0 RaRs
5: Night Of The Living Dead 1968 720p BDrip x264 AAC V4G
```

##### Select:
```bash
$ magnet "Night of the Living Dead 1968" 1
magnet:?xt=urn:btih:F17FB68CE756227FCE325D0513157915F5634985&dn=night+of+the+living+dead+1968+720p+brrip+x264+x0r&tr=udp%3A%2F%2Fopen.demonii.com%3A1337%2Fannounce
```

##### Stream:
Supply `--` and the magnet is sent to peerflix. All options after `--` are passed to peerflix.
```bash
$ magnet "Night of the Living Dead 1968" 1 -- --vlc
# this starts downloading the torrent via peerflix
```

Note that Night of the Living Dead [1968] is in the public domain. Download responsibly.

## Installation

```bash
npm install -g magnet-cli
# optional, if you also want to stream/download:
npm install -g peerflix
```
