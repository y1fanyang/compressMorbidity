
##################################################################### 

# MPD data are in wide format. To revert to MPD data to a long-formatted panel
# dataframe object, use following code

#####################################################################

# setwd(...)
df <- read_csv('fragility_longitudinal_mpd.csv')
var_vec <- c('id', 'date_born', 'date_exit', 'exit_reason', 'sex', 'diet', 'strain', 'has_clinical_record')
df_long <-
  df %>%
  pivot_longer(
  -var_vec,
  names_to = c(".value", "n"),
  names_sep = "_(?!.*_)",
  values_drop_na = T
)