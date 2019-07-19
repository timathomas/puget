[![CircleCI](https://circleci.com/gh/uwescience/puget.svg?style=svg)](https://circleci.com/gh/uwescience/puget)
[![codecov](https://codecov.io/gh/uwescience/puget/branch/master/graph/badge.svg)](https://codecov.io/gh/uwescience/puget)

# puget

Tools for munging data from Puget Sound Region tri-county HMIS.

## Modules:
- utils
- preprocess
- cluster
- recordlinkage
- tests

## Dependencies:

- pandas
- numpy
- scipy
- networkx
- recordlinkage
- matplotlib
- pytest (for testing)
- sphinx (for docs)


## Steps:
   raw data => 1 row per individual per enrollment (each county)
       `raw2individual_enrollments`
   => 1 row per family per enrollment (optional, general - belongs in `???`) -
       `individuals2families`
   => 1 row per family/individual per episode (general - belongs in `???`) -
       `enrollments2episodes`
   =>

---

## Codebook

	Codebook: PID's and SSN's
	pid0 = personal ID from pha and hmis - Alastair's linkage and HMIS ID's
	pid1 = generated pid by Tim within pha and hmis - unique id for each row
	pid2 = generated pid by Tim after df merge - unique id for each row
	ssn_dq =
		1 = 9-digit ssn or HMIS dq == 1
		2 = less than 9 digits or HMIS dq == 2
	    3 = NA, all same digit, or HMIS dq == 3
	ssn  = original ssn
	ssn1 = ssn quality == 1 and 9 digits
	dob1 = dob that is not in the list of very frequent 1/1 dates