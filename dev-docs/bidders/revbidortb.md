---
layout: bidder
title: RevBid OpenRTB
description: Prebid RevBid OpenRTB Bidder Adapter
biddercode: revbidortb
aliasCode: revantage
tcfeu_supported: true
gvl_id: 1588
usp_supported: true
gpp_sids: tcfeu, tcfca, usnat, usstate_all, usp
coppa_supported: false
schain_supported: true
dchain_supported: false
userId: all
media_types: banner, video
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

RevBid OpenRTB is an alias of the Revantage adapter. To get started, contact [adops@revantage.io](mailto:adops@revantage.io) to obtain a Feed ID.

### Bid Params

{: .table .table-bordered .table-striped }
| Name     | Scope    | Description                              | Example        | Type     |
|----------|----------|------------------------------------------|----------------|----------|
| `feedId` | required | Feed identifier assigned to your account | `'abc123xyz'`  | `string` |

### Banner Example

```javascript
var adUnits = [{
  code: 'banner-div',
  mediaTypes: {
    banner: { sizes: [[300, 250], [728, 90]] }
  },
  bids: [{
    bidder: 'revbidortb',
    params: { feedId: 'abc123xyz' }
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
      mimes: ['video/mp4', 'video/webm'],
      protocols: [2, 3, 5, 6],
      api: [1, 2],
      minduration: 5,
      maxduration: 30
    }
  },
  bids: [{
    bidder: 'revbidortb',
    params: { feedId: 'abc123xyz' }
  }]
}];
```

### User Syncing

```javascript
pbjs.setConfig({
  userSync: {
    filterSettings: {
      iframe: { bidders: ['revbidortb'], filter: 'include' },
      image:  { bidders: ['revbidortb'], filter: 'include' }
    }
  }
});
```
