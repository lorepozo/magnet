# magnet

A command-line search scraper for a torrent's magnet link. It can pass the magnet (and additional parameters) through to [peerflix](http://github.com/mafintosh/peerflix) to start downloading (and streaming) the search result automatically.

This utility scrapes search results from [torrentz.eu](http://www.torrentz.eu), and scrapes magnet links out of some resulting sites.

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

##### Selection:
```bash
$ magnet "Night of the Living Dead 1968" 1
magnet:?xt=urn:btih:F17FB68CE756227FCE325D0513157915F5634985&dn=night+of+the+living+dead+1968+720p+brrip+x264+x0r&tr=udp%3A%2F%2Fopen.demonii.com%3A1337%2Fannounce
```

##### Streaming:
All options after `-p/--peerflix` are passed to peerflix.
```bash
$ magnet "Night of the Living Dead 1968" 1 --peerflix --vlc
# this starts downloading the torrent via peerflix
```

Note that Night of the Living Dead [1968] is in the public domain. Download responsibly.

## Installation

```bash
git clone https://github.com/lukedmor/magnet
cp magnet/magnet /opt/local/bin/magnet
```

If you don't have peerflix, `npm install -g peerflix`
