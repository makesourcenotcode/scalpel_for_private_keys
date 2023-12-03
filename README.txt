=== SUMMARY ===

Scalpel was/is a useful data carving tool both for purposes of digital forensics
and helping regular folks recover accidentally deleted data. While it supports a
lot of data types/formats it doesn't yet support any kinds of deleted private
key data. If you accidentally deleted a private key file maybe we can help.

=== VERSION ===

1.0.0

=== USAGE ===

The kind of data Scalpel can carve out is controlled/limited by whatever
configuration file is passed to it via the -c command line option. All that
scalpel_for_private_keys really does is provide a ready made configuration file
you can use out of the box instead of worrying about writing correct rules by
hand when you're already stressed out from having deleted your private key file
and have trouble thinking straight. Usage looks approximately like:

scalpel -c scalpel_for_private_keys.conf <path_to_raw_device_file_or_disk_image>

If the deleted key is large you may want to adjust the maximum carve out size in
the third column of uncommented config lines.

=== IMPORTANT NOTE FOR THE MORE TECHNICAL USERS WHO CAN ACT ON IT ===

If the deleted key is on a Solid State Drive and the drive supports the TRIM
command pray it hasn't run since the deletion. If continuous TRIM is enabled
you are likely screwed. If periodic TRIM is enabled disable it immediately
before it has a chance to run again. Keep TRIM disabled until after a rigorous,
systematic, and hopefully successful recovery attempt has been made.

=== LICENSE ===

This is a Freedom Respecting Technology based on the apparently radical belief
that Open Source and Open Knowledge should be for everyone and not just well off
people with reliable Internet connections. Learn more at:
https://makesourcenotcode.github.io/freedom_respecting_technology.html

It's (admittedly small) Open Knowledge Set consists of:
* the main program configuration/database file scalpel_for_private_keys.conf
* the documentation / Help Information Set consisting of this file

Both are released to the Public Domain.

=== MOTIVATION ===

This should have been written in 2018 when I experienced a catastrophe with a
deleted OpenPGP private key. This is one of the things I wish was available for
me at the time. Though not a part of this project's documentation that story is
Solidly Entertaining and can be found by interested parties at:
https://makesourcenotcode.github.io/LispNYCSlides.pdf

=== LIMITATIONS AND DIRECTIONS FOR FUTURE WORK ===

We support some private key types but not all the ones we would like to yet. Not
to mention there might be private key types we don't even know exist.

Perhaps the most pressing limitation is that while we support retrieval of ASCII
armored OpenPGP keys we don't yet support the binary format.

Patches and pull requests supporting new types of private keys or new formats
for partially supported key types will be gratefully received.

For quality control purposes we ask that all contributors have tested the rules
they are adding and have evidence that the key data of the type they are adding
support for can be recovered in at least some scenarios for deleted test keys.

Let's make this THE database to use to help people recover accidentally deleted
key data!

=== CHANGELOG ===

v1.0.0: initial implementation
