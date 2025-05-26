Developer Certificate of Origin (DCO)
-------------------------------------

In order to submit your code to OpenStack repositories, you will need to agree
to `Developer Certificate of Origin <https://developercertificate.org/>`_.
OpenStack utilizes the Developer Certificate of Origin (DCO) as a lightweight
means to confirm that you are entitled to contribute the code you submit.
This ensures that you are providing your contributions under the project's
license and that you have the right to do so.

The Developer Certificate of Origin is as follows::

    Developer Certificate of Origin
    Version 1.1

    Copyright (C) 2004, 2006 The Linux Foundation and its contributors.

    Everyone is permitted to copy and distribute verbatim copies of this
    license document, but changing it is not allowed.


    Developer's Certificate of Origin 1.1

    By making a contribution to this project, I certify that:

    (a) The contribution was created in whole or in part by me and I
        have the right to submit it under the open source license
        indicated in the file; or

    (b) The contribution is based upon previous work that, to the best
        of my knowledge, is covered under an appropriate open source
        license and I have the right under that license to submit that
        work with modifications, whether created in whole or in part
        by me, under the same open source license (unless I am
        permitted to submit under a different license), as indicated
        in the file; or

    (c) The contribution was provided directly to me by some other
        person who certified (a), (b) or (c) and I have not modified
        it.

    (d) I understand and agree that this project and the contribution
        are public and that a record of the contribution (including all
        personal information I submit with it, including my sign-off) is
        maintained indefinitely and may be redistributed consistent with
        this project or the open source license(s) involved.




Every commit you make to an OpenStack project must be signed off by you. This
can be done by adding a line to your commit message::

    Signed-off-by: Your Name <your.email@example.com>

With this, you are certifying that you have the right to submit the work and
that you are doing so under the project's license.

.. _DCO Setting Up Your Git Configuration:

Setting Up Your Git Configuration for DCO
=========================================

To ensure your commits are automatically signed off, or to make it easier to
manually sign them off ensure that you configure your user name and email
address. The `Signed-off-by:` line will use the name and email address
configured in your Git client. Ensure these are set correctly and match the
name and email you use for your contributions.

You can then commit and sign-off using the `-s` (or `--signoff`) flag with
`git commit` command:

.. code-block::

    git commit -s

Adhering to these best practices will help ensure your contributions are
accepted smoothly:

* **Always Sign Off:** Every commit must include a `Signed-off-by:` line. If
  you amend a commit or rebase an existing change, you may need to sign off the
  new commit even if you're not the original author.
* **Use Your Real Name and Email:** The name and email address in
  your `Signed-off-by:` line should match the name and email configured in
  your `review.opendev.org (Gerrit)` account.
* **Rebasing and Squashing:** When rebasing or squashing commits, new commit
  hashes are generated. This means you will need to re-sign off the commits.
  If you are interactive rebasing, ensure that for each `pick` or `reword`
  action, you add the `-s` flag if you're manually running `git commit`.

Example Commit Message
======================

A typical commit message with a DCO sign-off will look like this:

.. code-block::

    Add feature X to OpenStack compute

    Introduces a new API endpoint for managing compute instances
    more efficiently. Includes updated documentation and tests.

    Closes-Bug: #12345
    Signed-off-by: Your Name <your.email@example.com>
    Change-Id: 8244cbaf1c12ddc90843fe204e107192c96f6bb3

A commit message with multiple authors and a DCO sign-off will look like this:

.. code-block::

    Add feature X to OpenStack compute

    Introduces a new API endpoint for managing compute instances
    more efficiently. Includes updated documentation and tests.

    Closes-Bug: #12345
    Co-authored-by: Another Contributor <another.contributor@example.com>
    Signed-off-by: Your Name <your.email@example.com>
    Signed-off-by: Another Contributor <another.contributor@example.com>
    Change-Id: 277ad6ef2721a7081a9db10f63353b407c8b1ca8

.. note::

   Subsequent developers who co-author or otherwise help shepherd a
   contribution in some way must add their own `Signed-off-by` attestation.
   `Co-authored-by` entries are not **required**, since `Signed-off-by`
   is treated as equivalent. The use of `Co-authored-by` is recommended to
   accommodate any legacy tooling that credits all authors of a change.
