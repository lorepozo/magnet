# magnet

Search. Select. Stream.

__`magnet`__ is a command-line torrent search scraper for magnet links. It can pass a selected magnet (and additional parameters) through to [peerflix](http://github.com/mafintosh/peerflix) to start downloading (and streaming) the search result automatically. Or you could pipe the output from __`magnet`__ into your preferred torrent utility!

This utility gets search results and magnet links from [thepiratebay.org](https://thepiratebay.org). The responsibility lies upon the user to not download malicious, false or illegal material using this tool.

The search isn't limited to _just_ video, of course!
```bash
$ magnet "Ubuntu" 1 --
```

## Usage

### Basic

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

### Advanced

##### More/fewer results

You can choose how many results to show with the `--rows` option:
```bash
$ magnet --rows=10 "Night of the Living Dead 1968"
1: Night of the Living Dead 1968 (1080p, x265, AAC 1.0)
2: George Romero 1968-1985 Night Dawn and Day Of The Living Dead
3: Night of the Living Dead[1968]DvDrip[Eng]-Stealthmaster.avi
4: Night.Of.The.Living.Dead.1968.720p.BluRay.x264-CtrlHD [PublicHD]
5: Night Of The Living Dead 1968 Colorized DVDrip x264-[MULVAcoded]
6: Night of the Living Dead (1968) - In Colour - DivX  [akhiugo]
7: Night Of The Living Dead (Millennium Edition; 1968).avi
8: Night of the Living Dead (1968)
9: Night Of The Living Dead [1968 - 30th Anniversary Edition]
10: Night Of The Living Dead 1968 720p_sujaidr
```

##### Download using other torrent clients

You may prefer to use another torrent client using the output from **`magnet`**
```bash
# rtorrent
$ tr=`magnet "Night of the Living Dead 1968" 1`
$ rtorrent "$tr"

# clipboard (macOS) to paste into a GUI torrent client
$ magnet "Night of the Living Dead 1968" 1 | pbcopy

# clipboard (X on GNU/Linux) to paste into a GUI torrent client
$ magnet "Night of the Living Dead 1968" 1 | xclip -i -sel clipboard
```


Note that Night of the Living Dead [1968] is in the public domain. Download responsibly.

## Installation

```bash
npm install -g magnet-cli
# optional, if you want to stream/download using '--' as shown in the Basic Usage section:
npm install -g peerflix
```
