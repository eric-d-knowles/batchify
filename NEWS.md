# batchify 0.1.1

* Declare dependency on R (>= 4.1.0), required for use of the native pipe
  (`|>`) and function shorthand (`\(...)`) syntax. Flagged by CRAN incoming
  checks.
* Remove single quotes around file extensions in the DESCRIPTION
  `Description` field.
* Replace `\dontrun{}` with runnable examples where possible. The one
  remaining `\dontrun{}` (`make_sbatch(..., submit = TRUE)`) requires a real
  Slurm cluster and cannot be executed on CRAN's check servers.
* `make_sbatch()` no longer writes to the current working directory by
  default. `log_dir` now defaults to `NULL` and resolves to the same
  directory as `out_file` instead of a hardcoded `"logs"` under `getwd()`.

# batchify 0.1.0

* Initial release.
* `batchify()`: convert a notebook to an R script and submit as a Slurm batch job.
* `make_sbatch()`: generate a Slurm batch script for an R job.
* `capture_code()`: extract R code from `.R`, `.Rmd`, `.qmd`, and `.ipynb` files.
* `launcher` argument to `make_sbatch()`/`batchify()`: prepend a command prefix to the `Rscript` call, e.g. `"numactl --interleave=all"`.
