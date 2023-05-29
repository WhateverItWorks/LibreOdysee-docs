Librarian is now testing [InstancePage](https://codeberg.org/video-prize-ranch/InstanceTools) for an instance list and redirection. InstancePage provides a refreshed user interface and new features. It can be found at [https://librarian.codeberg.page/](https://librarian.codeberg.page/).

## Instance selection
Replacing odysee.com or an instance domain with `librarian.codeberg.page` and adding `#/` after the first slash will let you use the InstancePage as an instance selection page. Instance status and sorting will be available at a later date.

Example:
`https://lbry.bcow.xyz/@fireship:6` -> `https://librarian.codeberg.page/#/@fireship:6`

> Redirection without `#/` will be available once this is supported by [Codeberg Pages](https://codeberg.org/Codeberg/pages-server/issues/46).

> A button to randomly select an instance will be available at a later date.

> JavaScript is used to perform client side redirection for better privacy and performance. Using `#/` protects URL paths and never sends them to Codeberg Pages.

## Reporting issues
Issues should be reported to [InstancePage](https://codeberg.org/video-prize-ranch/InstanceTools).