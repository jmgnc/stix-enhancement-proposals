# STIX Enhancement Proposals (SEPs)
For demonstrating how SEPs might work.

# What is the problem we're trying to solve?
## tl;dr
SEPs are intended to establish a mechanism for folks to suggest their
ideas in a common structure, recruit others to help, and iterate on
bleeding-edge stuff in an interoperable manner without degrading the
ecosystem of production tools that only expect CS/CSD level inputs.

It's not just enough having a great idea. For that idea to translate
into reality, you have to educate your fellow TC participants, recruit
co-sponsors to help with the work, and gradually build consensus. This
process aims to make that easier.

## Background
Things can move pretty slowly in a consensus-based standards body and
good ideas can get bogged-down in committee. Part of the resistance to
new ideas in STIX2 is that the technical committee's risk appetite has
shifted towards demanding a higher level of vetting before changes get
pulled into the formal work process. Meanwhile there are folks trying
to tackle real-world problems who can't wait on changes to the formal
specifications to be finalized. STIX2 supports for custom objects and
properties, but while these are sufficient to address the needs of
vendor-specific implementations they are not interoperable.

# Scope
* Defining new STIX SDOs as SEPs
* Defining new STIX Cyber Observables (SCOs) as SEPs
* Defining named sets of custom properties to add functionality to
  existing STIX SDOs and SCOs (as in, specified in a CSD or CS) as
  SEPs
  * In the context of SCOs this will must align with the concept of
    Custom Observable Extensions defined in STIX 2.0, Part 3.
	* It's unclear how this would work with Patterning if you're
      trying to match against a SEP-defined property within an
      existing object.

# SEPs for new SDOs
1. Clone this repository.
2. Give your SEP a name and create a corresponding directory
   within `seps/draft/sdos/`.
3. Copy `templates/sdo_sep_template/template.md` and
   `templates/sdo_sep_template/template.json` into the directory
   you just created (s/template/your SEP name).
4. Start by filling out as much as you can of <your SEP name>.md.
5. Ping the CTI TC on #general, let folks know what you're working on
   and where to find it.
6. Create a dedicate CTI TC Slack channel for collaboration.
7. Define the object's schema in <your SEP name>.json
8. Rinse and repeat on Slack and minigroup working calls until you
   feel the work is ready to be presented to the wider CTI TC.
9. Barring substantive objections by the CTI TC, do a pull request
   against this git repo.
10. ...profit!

## An example, plus how the hell this is supposed to work...
If you look under `seps/draft/sdos/x-oasis-cti-tc-grouping/` you'll
see the Grouping proposal (taken from the STIX 2.1-Working Concepts
Google Doc) defined as a SEP. There's Markdown (for the humans) and
JSON Schema (for the machines.)

The idea is that if you receive a custom object prefixed with
`x-oasis-cti-tc-*`, then you know to look in `manifest.md` to figure
out what type of SEP it is, where to find the associate descriptive
text and schema, as well as the latest version (based on the git
commit SHA1 hash).

# TODO
- [ ] finish example for SCO SEPS (a la x-oasis-cti-tc-grouping)
- [ ] figure out how to handle SEPs that add new properties or sets of properties to existing SDOs and SCOs
- [ ] talk through the draft, active, and deprecated statuses
