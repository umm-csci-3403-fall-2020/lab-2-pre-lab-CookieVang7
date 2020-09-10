# Leak report

The memory leak was the "cleaned" variable in the is_clean function of clean_whitespace.c. 

When the function called cleaned=strip(str), it allocated some memory to cleaned. Cleaned was used in return = strcmp(str,cleaned) and never freed which was causing the leak. 

If cleaned was an empty string, the free method would break, so I only called free(cleaned) in an if statement which first checked to see if cleaned was not empty.
