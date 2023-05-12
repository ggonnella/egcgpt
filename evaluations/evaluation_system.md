# organization

## metadata of each rule

quality: quality tag, as defined below
rule_id: ID or none, if the rule did not exist
errors: [ array of error tags, see below ]
notes: { "note_tag": "note", ... }
(note_tag can be e.g. an error tag)

# quality

depend on the type and quantity of the error

The quality is one of the following:
- excellent: no error or incorrections
- good: one or very few incorrections and minor errors
- fair: several incorrections and minor errors
- poor: at least one major error
- junk: multiple major errors

# counts

counts of existing rules and their relations to output:
  excellent, good, fair, poor, junk: corresponding to existing rules
  ..._split: if existing rule is split into multiple (average qualities)
  ..._joined: if existing rules are joined (the existing are count)
  missing: number of exiting rules which were not defined

counts of rules in output not present in existing:
  new_wrong: not present in existing rules, since not correct
  new_too_generic: rule is not included in manually curated
               dataset, since too generic and uninteresting
  new_overlapping: implied by another rule (e.g. more generic)
  new_small_group: rule is not included in manually curated
                dataset, since it concerns a single strain or species

# error tags

incorrect/unknown: not really correct, but still reasonable
  (for non-categorical use incorrect, for categorical diff is listed/unlisted)
wrong: not reasonable, but elsewhere could be still correct
invalid: nonsense, out of scope
missing: empty or equivalent, e.g. a dot
multi: correct, but non-atomary, could have been splitted

For categorical variables:

           | correct | listed | reasonable | in_scope | present |
-----------|---------|--------|------------|----------|---------|
multi      | yes     | yes    | yes        | yes      | yes     |
incorrect  | no      | yes    | yes        | yes      | yes     |
wrong      | no      | yes    | no         | yes      | yes     |
unknown    | no      | no     | yes        | yes      | yes     |
invalid    | no      | no     | no         | no       | yes     |
missing    | no      | no     | no         | no       | no      |

For other variables:

           | correct | reasonable | in_scope | present |
-----------|---------|------------|----------|---------|
multi      | yes     | yes        | yes      | yes     |
incorrect  | no      | yes        | yes      | yes     |
wrong      | no      | no         | yes      | yes     |
invalid    | no      | no         | no       | yes     |
missing    | no      | no         | no       | no      |

variable names:
  group_def (= group name, or group name and group type)
  group_type
  quantifier
  content_def (= content name, or content name and content type)
  content_type
  mode
  region
  comparison (= operator and reference data)
  operator
  reftype (= reference type)
  value (= reference data, if reference type is value)
  refgroup (= reference data, if reference type is group)

unknown_key: there are additional keys in the answer
missing_key: some keys are missing in the answer
too_generic: see above
overlapping: see above
small_group: see above
