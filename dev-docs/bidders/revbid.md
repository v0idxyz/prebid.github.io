---
layout: bidder
title: RevBid
description: Prebid RevBid Bidder Adapter
biddercode: revbid
aliasCode: bidfabrik
tcfeu_supported: true
gvl_id: 1588
usp_supported: true
gpp_sids: tcfeu, tcfca, usnat, usstate_all, usp
coppa_supported: false
schain_supported: true
dchain_supported: false
userId: all
media_types: banner, video, native
safeframes_ok: true
deals_supported: true
floors_supported: true
fpd_supported: true
pbjs: true
pbs: false
prebid_member: false
multiformat_supported: will-bid-on-one
ortb_blocking_supported: false
privacy_sandbox: no
sideload_disabled: false
---

### Registration

To use the RevBid adapter, contact [prebid@revbid.net](mailto:prebid@revbid.net) to obtain a Feed ID.

### Bid Params

{: .table .table-bordered .table-striped }
| Name   | Scope    | Description                                       | Example              | Type     |
|--------|----------|---------------------------------------------------|----------------------|----------|
| `feed` | required | Feed identifier assigned to your account          | `'pub-4417'`         | `string` |
| `host` | optional | Custom RTB host (defaults to `bid.bidfabrik.com`) | `'us.bidfabrik.com'` | `string` |

### Banner Example

```javascript
var adUnits = [{
  code: 'banner-div',
  mediaTypes: {
    banner: { sizes: [[300, 250], [728, 90]] }
  },
  bids: [{
    bidder: 'revbid',
    params: { feed: 'pub-4417' }
  }]
}];
```

### Video Example

```javascript
var adUnits = [{
  code: 'video-div',
  mediaTypes: {
    video: {
      context: 'instream',
      playerSize: [[640, 480]],
      mimes: ['video/mp4'],
      protocols: [2, 3, 5, 6]
    }
  },
  bids: [{
    bidder: 'revbid',
    params: { feed: 'pub-4417' }
  }]
}];
```

### Native Example

```javascript
var adUnits = [{
  code: 'native-div',
  mediaTypes: {
    native: {
      title: { required: true },
      image: { required: true, sizes: [[300, 250]] },
      body: { required: false }
    }
  },
  bids: [{
    bidder: 'revbid',
    params: { feed: 'pub-4417' }
  }]
}];
```

### User Syncing

```javascript
pbjs.setConfig({
  userSync: {
    filterSettings: {
      iframe: { bidders: ['revbid'], filter: 'include' },
      image:  { bidders: ['revbid'], filter: 'include' }
    }
  }
});
```
