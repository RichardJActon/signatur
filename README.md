# signatur (typeR?)
Gradual typing function signatures for R

```
parse_sigs <- function(sigs_vec) {
  # return a list of testing functions
  e.g. for "i" is.integer()
}

xfun <- function(..., expr) {
  args <- list(...)
  sigs <- purrr::map_chr(args, ~.x[[1]])
  check_funs <- parse_sigs(sigs)
  # purrr::map2(args, check_funs, ~.y(.x)) # pre-checking defaults
  
  # metaprogramming to construct return function
  # check_funs applied to args prior to expr
  # args for new function from 
  # expr to function body
}

my_fun <- xfun(list("i",x = 1:3),list("I", y = 2L), {
  x*y
})

my_fun(1:5, 3)
```
