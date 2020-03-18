# Webring

This [webring](https://wiki.xxiivv.com/webring) is an attempt to inspire artists & developers to create and maintain their own website and share traffic among each other. The webring's aim is to share rich hand-crafted websites such as **diaries, wikis & portfolios**.

## Join the webring

```
<a href='https://webring.xxiivv.com/#random' target='_blank'><img src='https://webring.xxiivv.com/icon.black.svg'/></a>
```

1) Add the webring icon to your website html.
2) Add your website information to the [sites.js](https://github.com/XXIIVV/webring/edit/master/scripts/sites.js) file. See all options below, and be mindful of what's required for each part of the webring.
3) Submit a Pull Request with **the location of the webring icon** on your site. Pull requests with blank descriptions will be rejected.

Alternatively, if you your website has a dark background, use `icon.white.svg`. If your website is complaining about *https*, go ahead and host the icon yourself.

Only the `url`, `contact`, and `langs` keys are required to join the webring. Below you can find a list of all the available keys for the various areas of the webring.
``` js
{
  /* REQUIRED */
  contact: <string used to contact if necessary>,
  langs: <array of represented languages (iso codes) ex. ['en', 'fr']>,
  url: <string url used for Portal>,

  /* also possible */
  rss: <string url for rss or atom feed>,
  title: <string displayed alphanumeric name, used for the Portal>,
  type: <string used for the Portal, ex. 'blog'>,

  /* for WIKI */
  author: <string used in WIKI and HALLWAY>,
  wiki: <string url for the .ndtl file>,

  /* for HALLWAY */
  feed: <string url for the .twtxt file>
}
```

### Webring criteria

**Single page websites, websites acting only as portals to other social platforms, or websites with violent, racist, sexist or speciesist content will be rejected**.

The aim of the webring is to display **hand-crafted personal** websites showcasing the creator's audio, visual or written work. Your business site is probably not the best fit for the webring, and will be rejected.

If it's seen that your website is in violation to any of these rules your site will be removed from the webring. If you fix the issues, feel free to submit another PR to join back in.

### Circular Linking

Instead of linking to the directory, you can also link to the next link in the ring by adding parts of your site or domain in the hash of the request url:

```
<a href='https://webring.xxiivv.com/#wiki.xxiivv' target='_blank' rel="noopener noreferrer"><img src='https://webring.xxiivv.com/icon.black.svg'/></a>
```

### Joining the hallway

[The Hallway](https://webring.xxiivv.com/hallway.html) is a decentralized forum using [twtxt](https://twtxt.readthedocs.io/en/stable/user/twtxtfile.html) feeds.

To join, create a `.txt` file on your site, add its URL to [your webring entry](https://github.com/XXIIVV/Webring/blob/master/scripts/sites.js) as `feed`, and fill in your desired name in the `author` key. The content of the file should be a dateISO string, a tab(or 3 spaces) and a message:

```
2016-02-04T13:30:00+01:00   You can really go crazy here! ┐(ﾟ∀ﾟ)┌
2016-02-03T23:05:00+01:00   @<example http://example.org/twtxt.txt> welcome to twtxt!
2016-02-01T11:00:00+01:00   This is just another example.
2015-12-12T12:00:00+01:00   Fiat lux!
```

You don't need to allow all origins nor allow any other methods rather than GET, doing so can harm the security of your website, please read about [Cross-Origin Resource Sharing](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) if you intend to do anything more complicated. If you're looking for client, we recommend using [twtxtc](https://hub.darcs.net/dertuxmalwieder/twtxtc/changes).

### Joining the wiki

[The Wiki](https://webring.xxiivv.com/wiki.html) is a decentralized encyclopedia using [ndtl](https://wiki.xxiivv.com/Indental) feeds.

To join, create a `.ndtl` file on your site, and add its URL to [your webring entry](https://github.com/XXIIVV/Webring/blob/master/scripts/sites.js) using the `wiki` key.

## Webring CLI

If you'd prefer to interact with the webring through your terminal, you can clone or install the [webring-cli](https://github.com/ckipp01/webring-cli).

## API

This repository does not contain mature API capabilities, but there are a couple ways to request a list of sites and other information currently in the webring.

- Request [sites.js on xxiivv](https://webring.xxiivv.com/scripts/sites.js) or [sites.js on github](https://raw.githubusercontent.com/XXIIVV/webring/master/scripts/sites.js) and parse it. An example can be seen [here](https://gist.github.com/ckipp01/2ab7ac42e2837b4359efeb76eb49bb54).

## Need Help?

The ring is managed by [@neauoire](https://twitter.com/neauoire), but any member of the network is also welcome to join this repository as a collaborator to help manage new links and Pull Requests. Read more about the webring [here](https://wiki.xxiivv.com/webring).
