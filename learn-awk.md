```awk
    # print first column
    awk '{ print $1}' src.txt
    
    # print line number
    awk '{ n++ } END { print n }' src.txt
    awk 'END { print NR }'
    
    # pipe who.count()
    awk 'BEGIN { { while ( "who" | getline ) n++ } print n }'
    who | awk '{ n++ } END { print n }'
    
    # word-start-with-A / min-value 100
    $1 ~ /^A.*/ { $3 *= 1.05 } $3 < 100 { $3 = 100 }
    
    # set ( array ) count
    awk '{ for (i = 2; i <= NF; i++) Numbers[$i] ++ } END { for (course in Numbers) printf("%10s %d\n", course, Numbers[course] }' src.txt
    
    # redirect
    awk 'BEGIN { print "header" > "outFile.txt"  }'
```