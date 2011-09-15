Version 0.1.2 (in development)
------------------------------

* Added LowPoly.make_random to generate random polyhedral lower
  previsions.

* Added Gamble.minimum and Gamble.maximum methods.

* Added LowPoly.stabilize method to work around numerical
  instabilities for instance in the random generator.

* Refactored PSpace/Gamble/Event system to make it easier to work with
  multivariate problems.

  - PSpace is replaced by two classes: Var and Domain. Var is a
    fundamental variable which is logically independent of all other
    variables. Domain consists of a collection of these variables.

  - Gamble and Event now derive from Func, which describe variables
    that are defined as functions of other variables, on arbitary
    domains.

Version 0.1.1 (13 June 2011)
----------------------------

* Fixed calculation of conditional credal set.

* Added SetFunction.get_choquet to calculate the Choquet integral
  (contributed by Erik Quaeghebeur).

* Added __radd__, __rmul__, and __rsub__ for Gamble (contributed by
  Erik Quaeghebeur).

* Event.__sub__ now only does set difference with a collections.Set
  (so Event minus Gamble will be a Gamble via Gamble.__radd__, but
  Event minus Event is an Event).

* Event.__init__ now raises a ValueError when creating an event with
  elements that are not in the possibility space, instead of silently
  omitting them (fixes issue #3, reported by Erik Quaeghebeur).

* LowProb.extend now has default upper=False argument, as it would
  raise a ValueError instead.

* New LowPrev.get_extend_domain method which calculates the maximal
  domain to which the lower prevision can extend. This is now used if
  keys are not specified (or are None) when calling LowPrev.extend
  (addresses in part issue #4, reported by Erik Quaeghebeur).

* Prob.extend now has a 'linear' algorithm to spread remaining mass
  over undefined singletons uniformly (addresses in part issue #4,
  reported by Erik Quaeghebeur).

* Improved Choquet integral calculation so level sets are constructed
  at the same time that the values are ordered.

* Added SetFunction.get_bba_choquet method to calculate Choquet
  integral of a basic belief assignment.

Version 0.1.0 (24 August 2010)
------------------------------

* First release.
