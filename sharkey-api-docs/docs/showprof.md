# Show Profile
Finding a profile on Sharkey uses /api/users/show.
# Input
The payload input uses username & host.
Host is used for the fediverse URL where the profile is hosted.
For example, a payload to search for nomaakip on sharkey.nomaakip.xyz (looked up via sharkey.nomaakip.xyz) would look like this:

`{username: "nomaakip", host: null}`