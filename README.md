# jq-documentation

## Find array members where a sub-array is length 0. 

Following case, check images with 0 length tags and print the digests for such images.

```bash
[
  {
    "digest": "sha256:03a0c47c7a855b11918e226e6c305387c8b8b1143944736b2c932fedc3b9f8e2",
    "tags": [
      "3a5f81eb00fd8b91e24f633255ca2ee48de9d0c6",
      "branch-use_kubernetes_monitor",
      "pr-545"
    ]
  },
  {
    "digest": "sha256:2779e62391a2a128429483201604848647d8770711571b55a0de90bfcc65363d",
    "tags": [
      "7f9d379a66dc57a3e1e60942ad2a6ede69086592",
      "branch-test_terminate",
      "pr-530"
    ]
  },
  {
    "digest": "sha256:d2771a3d6fcf86d5d839824d0c1ae8927d990289060cddf6504dcce97711d3cc",
    "tags": []
  },
  {
    "digest": "sha256:851708413bb5bfeaa9a6c74b74d2e1113b7bd2bbe61220aa360fa05ae79cb3a9",
    "tags": [
      "1.226.0",
      "staging"
    ]
  },
  {
    "digest": "sha256:85ff839d358ac8cee27115364a3063cdd800bcb5d9f6ef671cf16e46f47bd811",
    "tags": [
      "branch-fixCSR",
      "de9d4689b9794d688145e752ae5039688b76796a",
      "pr-544"
    ]
  },
  {
    "digest": "sha256:42723167a2a7d11c49cc4f442682360b87c678411a013a5e7f7a4027d5a465ab",
    "tags": [
      "801e082c983539659a345f64f7e7993bf62f0165"
    ]
  },
  {
    "digest": "sha256:00d13001a9432730cee65ee7ceb15067e506b8567202e0d93d3c130083a91240",
    "tags": [
      "1.225.0",
      "staged"
    ]
  },
  {
    "digest": "sha256:08809230b87df37fe00efdcbb48365e205b44ab5ddca41eae74a6a2820f8118c",
    "tags": [
      "1.224.0"
    ]
  },
  {
    "digest": "sha256:429ee13cd68bd4a8b9d11c8083f8026cb47e0428569b959b6dc73808688e4359",
    "tags": [
      "016e10fe4e812213d2849f188ec6c5df67e6c51f",
      "branch-fixidmapping",
      "pr-542"
    ]
  },
  {
    "digest": "sha256:a63d1a71f119455a5cb7654a50aa79a36531b99708db03059017f2fa86652d72",
    "tags": [
      "1.223.0"
    ]
  }
]
```

```bash
jq -r '.[] | select(.tags | length==0) | .digest'
```
