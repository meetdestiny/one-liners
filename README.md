# one-liners

#Remove newlines within quotes from csv files. Helps streaming large csvs instead of loading and parsing. 

awk -v RS='"' 'NR % 2 == 0 { gsub(/[\r\n]+/, " ") } { printf("%s%s", $0, RT) }'
