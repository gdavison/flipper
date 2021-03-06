## 0.7.1

* Fix bug where features with names that match static file routes were incorrectly routing to the file action (https://github.com/jnunemaker/flipper/issues/80)

## 0.7

* Added Flipper.groups and Flipper.group_names
* Changed percentage_of_random to percentage_of_time
* Added enable/disable convenience methods for all gates (ie: enable_group, enable_actor, enable_percentage_of_actors, enable_percentage_of_time)
* Added value convenience methods (ie: boolean_value, groups_value, actors_value, etc.)
* Added Feature#gate_values for getting typecast adapter gate values
* Added Feature#enabled_gates and #disabled_gates for getting the gates that are enabled/disabled for the feature
* Remove Feature#description
* Added Flipper::Adapters::PStore
* Moved memoizable decorator to instance variable storage from class level thread local stuff. Now not thread safe, but we can make a thread safe version later.

UI

* Totally new. Works like a charm.

Mongo

* Updated to latest driver (~> 2.0)

## 0.6.3

* Minor bug fixes

## 0.6.2

* Added Flipper.group_exists?

## 0.6.1

* Added statsd support for instrumentation.

## 0.4.0

* No longer use #id for detecting actors. You must now define #flipper_id on
  anything that you would like to behave as an actor.
* Strings are now used instead of Integers for Actor identifiers. More flexible
  and the only reason I used Integers was to do modulo for percentage of actors.
  Since percentage of actors now uses hashing, integer is no longer needed.
* Easy integration of instrumentation with AS::Notifications or anything similar.
* A bunch of stuff around inspecting and getting names/descriptions out of
  things to more easily figure out what is going on.
* Percentage of actors hash is now also seeded with feature name so the same
  actors don't get all features instantly.
