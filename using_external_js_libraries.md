# Using external JS/CSS libraries

*Often when using JS or CSS libraries they are included trough external sources (http/https). Since T3kit uses JS/CSS concatenation and compression those libraries will be downloaded to the  server each time the cache is cleared causing external request which in turn causes performance impact on the server. 

To prevent this from happening use the following settings for external files:

includeJS {
  jquery = https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js
  jquery.external = 1
  jquery.excludeFromConcatenation = 1
  jquery.disableCompression = 1
}
