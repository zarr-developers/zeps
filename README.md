# Zarr Enhancement Proposals (ZEPs)

## Community Feedback Process for Zarr Specifications

ZEP stands for Zarr Enhancement Proposal. A ZEP is a design document providing
information to the Zarr community, describing a modification or enhancement of
the Zarr specifications or a new feature for its processes or environment. The
ZEP should provide specific proposed changes to the Zarr specification and a
narrative rationale for the specification changes.

We intend ZEPs to be the primary mechanism for evolving the spec, collecting
community input on significant issues and documenting the design decision that
has gone into Zarr.

## Proposing a new ZEP

ZEPs should be submitted as a draft ZEP in the [draft folder](https://github.com/zarr-developers/zeps/tree/main/draft)
of this (*zeps*) repository via [GitHub pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).

The PR should contain the narrative text of the ZEP with the name `zep-<n>.md`
where `<n>` is an appropriately assigned four-digit number. The draft ZEP must
use the [ZEP X - Template and Instructions](https://zarr.dev/zeps/template/template.html)
file.

To read more on `Submitting a ZEP`, please refer [here](https://zarr.dev/zeps/active/ZEP0000.html#submitting-a-zep).

## Contributing to ZEPs

The ZEPs in this repo are published automatically on the web @
https://zarr.dev/zeps/. If you wish to contribute to the website, please build
the website locally on your machine. Building this website requires [Jekyll](http://jekyllrb.com/).
Refer to [this](https://jekyllrb.com/docs/) to install Jekyll.

Steps to contribute:

``` 
1. Fork this repo
2. cd into the forked repo
3. Type $ bundle exec jekyll
serve --incremental
4. Open a browser and go to localhost:4000/ to see the
website
5. Make desired changes, save them and refresh localhost:4000/ to see
the changes
```

Once done, push your changes to your fork and open a
[GitHub pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).

