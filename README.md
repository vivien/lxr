LXR command line tool

A (soon) improved version of the following trivial Bash script:

```` bash
#!/bin/bash

# lxr: open lxr website)
# lxr <term>:  open lxr search page for <term> (requires a pref cookie)

LXR_BASE_URL=http://lxr.linux.no/linux
LXR_LINUX_VERSION=
LXR_SEARCH_TERM="$@"

LXR_URL="$LXR_BASE_URL"
#TODO parse $@ for -v option
[[ -z "$LXR_LINUX_VERSION" ]] || LXR_URL="$LXR_URL+v$LXR_LINUX_VERSION"
[[ -z "$LXR_SEARCH_TERM" ]] || LXR_URL="$LXR_URL/+search?search=$LXR_SEARCH_TERM"

echo "xdg-open \"$LXR_URL\""
xdg-open "$LXR_URL" &

exit
````
