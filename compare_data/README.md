
Welcome to this report factory!
===============================

The factory will help you handle multiple `rmarkdown` reports at the same
time. Put your `.Rmd` files in `report_sources`, refer to any external files in
the `.Rmd` using `here::here()`, and you're sorted.


How the factory is organised
----------------------------

- `report_sources`: (mandatory) put your `.Rmd` documents there (subfolders are
  OK); they must be named as `[report_name]_[yyyy-mm-dd].Rmd`, for instance,
  `situation_report_2018-01-21.Rmd`
  
- `data/`: (recommended) put your data in this folder (subfolders are OK)

- `scripts/`: (recommended) put your external R scripts, used in your `.Rmd`
  reports, in this folder (subfolders are OK)
  
- `report_outputs/`: (automatically created) the factory will store report
  outputs there, using named and time-stamped folders



How to run the factory: useful commands
---------------------------------------

- `list_reports()`: lists reports currently stored in the factory (only `.Rmd`
  source files)

- `compile_report()`: compiles one single report, designated using the file name
  or a non-ambiguous match; outputs will be stored in `report_outputs/`

- `update_reports()`: compiles all report, using by default the most recent
  version of each report; outputs will be stored in `report_outputs/`



Suggested workflow
------------------
  
1. create a new factory using `new_factory()` and move into this new folder
   
2. go to `report_sources/`, write your `.Rmd` report, using the provided
   examples as inspiration; remove the examples files; make sure you use the
   naming conventions explained above, e.g. `foobar_2018-01-25.Rmd`.

3. check your report by compiling the `.Rmd` manually if needed,
   e.g. `rmarkdown::render("foobar_2018-01-25.Rmd")`; once you are happy with the
   results, **make sure you remove all output files from the source folder**
   
4. run `update_reports()` to generate all outputs, or
   `compile_report("foobar_2018-01-25")` if you just want to produce
   time-stamped outputs for this report; check results in the folder
   `report_outputs`
   
