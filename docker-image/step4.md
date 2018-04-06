Before `overlay`, `aufs` used to be the default storage driver of Docker.

The Katakoda hosts don't have support for `aufs` in the kernel, so we can't demonstrate here.

If you setup your own Docker daemon with `aufs` as the storage driver, try find out where the new layer is stored. And see what't stored in there.
