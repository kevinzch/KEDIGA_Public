# Quickly fix new Teams messages not showing up


## Issues

I encountered some issues with new Teams:
* New messages do not show up
* Messages aren't getting marked as read even when I open the chat
* I can't send new messages

These problems are specific to the new Teams; the (old) Teams works perfectly.
I attempted to resolve the by reinstalling Teams and clearing cache from the '%appdata%\Microsoft\Teams' directory, but it seems these methods only impact the old Teams and the issues persist in the new one.

## Solution

I found out that the cache for the new Teams is located at:

```
%localappdata%\packages\MSTeams_8wekyb3d8bbwe\Localcache\Microsoft\MSTeams
```

I deleted everything in that directory, then restarted my PC, and all those issues disappeared.

## Conclusion

It appears that the cache directory for new Teams is consistent (at least for now). The cache directory can also be accessed by clicking on **Settings** -> **General** -> **About Teams** -> **Third Party Notice** -> **Desktop**.

## References

* [Using GitHub Actions to Publish Hugo Site From Private to Public Repo](https://microsoft365pro.co.uk/2023/07/31/teams-real-simple-with-pictures-clear-cache-in-teams-2-1-client/).

*If you have any questions or advice, leave me a comment below and I will try my best to respond!*

