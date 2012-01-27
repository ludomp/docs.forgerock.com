# The docs.forgerock.org Idea

The docs.forgerock.org idea is to have one location where we publish
finished core documentation for ForgeRock projects at the time they release.

*Publish* means put it up for public view, and leave it there.

*Finished* means the core doc set you publish has gone through documentation
[review](https://wikis.forgerock.org/confluence/display/devcom/Review+Process),
and deemed ready for publication by the person in charge of the release.

This is why the docs.forgerock.org idea is not implemented as a wiki:
Published core documentation is technically accurate and complete with
respect to the release. It is done and dusted, rather than a work in
progress.

You can log bugs and request enhancements. Those nearly always get
fixed in a subsequent release.

*Core documentation* refers to distilled content that helps readers understand
and implement best practices, that provides the definitive reference for the
software, that is built from source code committed to the project SCM alongside
other code, and that ForgeRock refers to as the official documentation for a
release.

Readers have other forms of documentation available to them, from IRC logs
and mail, blogs and wikis, to books and articles. docs.forgerock.org exists
alongside these alternatives.

*ForgeRock projects* are at <http://forgerock.org/>.


# The Example

This project includes skeleton documentation sets with empty placeholder
documents. The example is intended to demonstrate layout rather than
demonstrate a finished result.


# Publishing Core Documentation

Publishing is a manual process for now.


## Building a Core Documentation Set To Publish

In the .pom for your project, make sure draft mode is turned off.

    <!-- <draftMode>yes</draftMode> -->

Then build your documentation as you normally would, for example
with `mvn clean site`.

## Preparing the Core Documentation Set For Publication

1.  Under `site/doc`, remove the .epub and .rtf.
2.  Under `site/doc`, rename the .pdf to include the version number in the
    name. For example, `OpenIDM-Release-Notes.pdf` becomes
    `OpenIDM-2.0.1-Release-Notes.pdf`.
3.  Add the `index.html` files that redirect by product and by version to
    the top-level `en/index.html` file.
4.  Replace `coredoc.css` files with `css/coredoc.css` (after reading comments).
5.  Move your updated `doc` directory under `product/version/en` in the site
    directory.


## Updating the Site For Publication

1.  Add links and a table of links for your new documentation set in the
    top-level `en/index.html` file.
2.  Update `js/docs.js` to include your product and version.
3.  Test your work.
4.  Publish.


# TODO

* Improve the look and feel.
* Published localized documentation.
* Script updates to the site, rather than rely on manual updates.
* Automate publishing so that it happens during release using Maven.


* * *
This work is licensed under the Creative Commons
Attribution-NonCommercial-NoDerivs 3.0 Unported License.
To view a copy of this license, visit
<http://creativecommons.org/licenses/by-nc-nd/3.0/>
or send a letter to Creative Commons, 444 Castro Street,
Suite 900, Mountain View, California, 94041, USA.

Copyright 2011-2012 ForgeRock AS