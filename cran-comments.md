## Resubmission

This is a resubmission. In this version I have:

* Added `Depends: R (>= 4.1.0)` to DESCRIPTION, as flagged by the CRAN
  incoming pretest (package code uses the native pipe and function
  shorthand syntax introduced in R 4.1.0).
* Removed single quotes around file extensions in the Description field.
* Replaced `\dontrun{}` with runnable examples wherever possible. The one
  remaining `\dontrun{}`, in `make_sbatch()`, wraps a call with
  `submit = TRUE`, which requires a real Slurm cluster and cannot be
  executed on CRAN's check servers.
* `make_sbatch()` no longer writes to the current working directory by
  default: `log_dir` now defaults to `NULL` and resolves to the same
  directory as `out_file` instead of a hardcoded `"logs"` under `getwd()`.

## R CMD check results

0 errors | 0 warnings | 1 note

* checking CRAN incoming feasibility ... NOTE
  New submission

## Test environments

- Local: R 4.4.3 on Red Hat Enterprise Linux 9.6 (x86_64)
