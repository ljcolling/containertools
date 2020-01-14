#' Generates a myBinder link
#'
#' @description
#' `genlink` returns a mybinder link to the for based on a binder repo that
#' contains the contents of a github repo
#'
#' @param binderrepo A url for the Github repo hosting the binder details.
#' Defaults to standard teaching repo at
#' \url{https://github.com/ljcolling/teaching-binder} (see Details)
#' @param gitrepo A url for the Github repo hosting a R Project
#' @param landing Set the landing location (default is R Studio)
#'
#' @details
#' The default Sussex University teaching binder is hosted at
#' \url{https://github.com/ljcolling/teaching-binder}. This binder contains
#' a number of standard packages including the tidyverse, the here packages,
#' and the packages needed for knitting documents.
#'
#' For this to work the binder repo needs to have access to nbgitpuller.
#' If you're unsure how to set this up, then examine the default binder
#' Important: Branchs are not currently enabled. Both binder repo and the git
#' repo will default to the MASTER branch
#'
#' @export
genlink <- function(gitrepo = NULL,
                    binderrepo = 'https://github.com/ljcolling/teaching-binder',
                    landing = 'rstudio',
                    returntype = "link"){

  binderstr = stringr::str_remove(string = binderrepo,pattern = "https://github.com/")

  binderlink = paste0('https://mybinder.org/v2/gh/',binderstr,"/master?urlpath=git-pull?repo=",
                      paste0(utils::URLencode(gitrepo,reserved = T),'%26%3Burlpath=rstudio%26%3Bbranch=master'))
  if(returntype == 'link'){
    return(binderlink)
  } else {
    return(paste0("[![Binder](https://mybinder.org/badge_logo.svg)](",binderlink,")"))
  }
}
