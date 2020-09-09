# Leak report

#The memory leak was the "cleaned" variable in the is_clean function of clean_whitespace.c. Before the function called return is where I inserted the free(cleaned) method.
#When the function called "cleaned=strip(str)", it allocated some memory to "cleaned". "Cleaned" was used in "return = strcmp(str,cleaned)" and never freed which was causing the leak.
