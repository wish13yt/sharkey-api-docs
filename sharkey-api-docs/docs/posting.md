# Posting
Posting on Sharkey uses the API URL "/api/notes/create" and takes input via JSON; like this:
```
{
  "text": null,
  "fileIds": [
    "randomlyGeneratedFileID"
  ],
  "poll": null,
  "cw": null,
  "localOnly": false,
  "visibility": "public",
  "reactionAcceptance": "nonSensitiveOnly"
}```

fileIds is only used if an image is provided. If an image is not attached, it will not be in the JSON at all.
Text will show in the form of a string if provided, and if not, will show as null.
# Reaction Acceptance
reactionAcceptance accepts input in the form of these options:
- nonSensitiveOnlyForLocalLikeOnlyForRemote (Non-sensitive only (Only likes from remote))
- null (All)
- likeOnlyForRemote (All (Only likes for remote instances))
- likeOnly (Only likes)
- nonSensitiveOnly (Non-sensitive only)
# Polls
Polls come in this format:
```
{
  "text": "wii sop channel",
  "poll": {
    "choices": [
      "1",
      "2"
    ],
    "multiple": false,
    "expiresAt": null,
    "expiredAfter": 6000
  },
  "cw": null,
  "localOnly": false,
  "visibility": "public",
  "reactionAcceptance": "nonSensitiveOnly"
}```

expiredAfter takes time in milliseconds. For example, 6 seconds would be 6000 ms.
expiresAt takes in Unix timestamps. For example, 1767160800000 is December 31st, 2025 at 12:00 AM.
If no poll is provided, null is used instead of the poll object.
# Content Warnings
The cw field accepts a string and will prevent viewing of a post until you click on "Show content"
The string in the cw field will be shown even without clicking on Show content.
# Defederation
localOnly accepts a boolean, and if true, will not show your post to other instances of Sharkey and other ActivityPub servers.
This also shows a rocket ship icon next to the time counter on your post.