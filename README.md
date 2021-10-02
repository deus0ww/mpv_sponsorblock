# mpv_sponsorblock
A fully-featured port of [SponsorBlock](https://github.com/ajayyy/SponsorBlock) for mpv.  
this is a fork from https://github.com/po5/mpv_sponsorblock, full credits go to [@po5](https://github.com/po5)

## Installation
#### Requirements
- Python 3

#### Install
Clone this repo somewhere onto your drive and use the `make` utility for installation:

```
git clone https://github.com/dariusjonda/mpv_sponsorblock.git
cd mpv_sponsorblock
make install
```
Doing so will create symlinks for the `sponsorblock.lua` and the `sponsorblock_shared` directory.

#### Uninstall
`cd` into your `mpv_sponsorblock` directory an type:
```
make clean
```
This will remove the symlinks from your mpv scripts folder (`~/.config/mpv/scripts`)

## Usage

#### Key bindings
- g to set segment boundaries
- h to upvote the last segment

These can be remapped with the following script bindings: `sponsorblock/set_segment`, `sponsorblock/submit_segment`, `sponsorblock/upvote_segment`, `sponsorblock/downvote_segment`

Add lines in the following format to your input.conf: `alt+g script-binding sponsorblock/set_segment`

#### Categories
Categories to be skipped can be specified in the `sponsorblock.lua` under the `categories` option.  
```
-- Categories to fetch
categories = "music_offtopic,sponsor,intro,outro,interaction,selfpromo",
```
More information regarding the available categories can be found in the [SponsorBlock Wiki](https://github.com/ajayyy/SponsorBlock/wiki/Types#category).

#### SponsorBlock Text display
the text messages that appear whenever SponsorBlock triggers a section of the video to be skipped can be skipped by setting the option `osd_text_show = false` inside the `sponsorblock.lua`.

## Frequently Asked Questions (FAQs)
**Q: Playing the selected media show a `[sponsorblock] database update failed.` error**  
**A:** to temporarily fix that set `local_database = false` in the `sponsorblock.lua`. Fore more information see [Issue](https://github.com/po5/mpv_sponsorblock/issues/31) from the official repo.
