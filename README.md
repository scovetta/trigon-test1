# Trigon evidence: github.com/scovetta/trigon-test1

Signed records of whether published packages were rebuilt from their source, the
append-only log that holds them, and an index for finding them. `trigon publish` writes
it; `trigon evidence sync`, `trigon lookup` and `trigon check` read it, and so can any
tool that verifies a C2SP checkpoint and an RFC 6962 tree.

## Origin

`github.com/scovetta/trigon-test1`

The name of this log, signed into every checkpoint and into every verdict's falsifying
command. It never changes; a successor log has an origin of its own.

## Keys

- The log key, which signs `log/checkpoint` (also `keys/log.vkey`):
  `github.com/scovetta/trigon-test1+01f5e199+AYceSnUTY0/UYiJS0JyqyJfXEHkcW1QB5/+YxfBR5BVT`
- The attestation key, which signs every record (also `keys/attestation.pub`): Ed25519
  `51473006e194c378a2452f82499ab779315ba698a81bf46e3c89df64e49a9259`, key id `ca88cbc13f71123f`

Pin both. The copies here are for people, and for trust on first use: a key read from
the repository it vouches for is only as good as that repository.

## Checkpoint rate

A new checkpoint appears once per publication, and at least every 7 days from a heartbeat
leaf when nothing else is published. A log whose newest leaf is older than that has
stopped, or is being withheld from you.

## Disputes

Every divergence names where it is disputed:

https://github.com/scovetta/trigon-test1/issues

To dispute a record, report it there with the record's digest, the name of its file
under `records/`, and what you believe is wrong. A record is never deleted: a correction
is a new record that supersedes it, and both stay in the log.

## Divergence feed

Where this repository publishes divergences, `feed/divergences.atom` is an Atom feed of
the most recent 200 of them, newest first, each linking its record and where to dispute
it. It is regenerated from the log in the commit that publishes each divergence; the
log holds every one.

## Website

`site/` is a static website of these results, regenerated from the log by every publication:
a page for each package and each record, with the command that checks it. Serve `site/`'s
files with copies of `records/`, `evidence/`, `log/` and `keys/` beside them, as the Pages
workflow in Trigon's `docs/using-trigon.md` does. A page is a view, not evidence: whoever can
push can change one until the next publication, and `trigon lookup` is the check.
