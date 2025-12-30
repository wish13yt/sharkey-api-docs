# Posting
Posting on Sharkey uses the API URL "/api/notes/create" and takes input via JSON; like this:
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
}
fileIds is only used if an image is provided. If an image is not attached, it will not be in the JSON at all.
Text will show in the form of a string if provided, and if not, will show as null.
# Reaction Acceptance
reactionAcceptance accepts input in the form of these options:
- nonSensitiveOnlyForLocalLikeOnlyForRemote
- null (all)
- likeOnlyForRemote
- likeOnly
- nonSensitiveOnly
# Polls
Polls come in this format:
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
}
expiredAfter takes time in milliseconds. For example, 6 seconds would be 6000 ms.
expiresAt takes in Unix timestamps. For example, 1767160800000 is December 31st, 2025 at 12:00 AM.