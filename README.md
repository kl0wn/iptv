# Custom IPTV Playlist Generator

This `repo` automatically self updates using a GitHub Action `cron` job that is set to run daily at midnight. We consume the source `m3u` data from the excellent `iptv-org` over at https://github.com/iptv-org/iptv .

The source `m3u` is downloaded, cleaned up filtered and then transformed. Finally we re-generate a new fresh `m3u` playlist.

## Custom generated m3u playlist

| description           | m3u url                                |
|-----------------------|----------------------------------------|
| custom IPTV playlist  | https://kl0wn.github.io/iptv/index.m3u |

# How to create your own custom channels list

* fork this repo
* there is a defined `whiteList` array in the `generate.ts` file, simply make sure that the `tvg-id` name matches in the original source files, you can then give it a nicer name as well as set the group name as well e.g "Sports" etc
* push the repo to your github account
* _(optional)_ setup GitHub pages, this will then give you a nice URL that you can point our IPTV players to.

## manually regenerate locally

assuming you have deno installed locally you can simply invoke the following at the root folder:

```shell
$ deno run --allow-net --allow-read --allow-write generate.ts
```
