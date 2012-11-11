Ruby one liner
==============

Content manipulation
--------------------
* Comment all lines

    ruby -pe '$_="\# #{$_}"'

    ruby -pe 'gsub(/^/, "\# #{$1}");'


File operations
---------------

* Prepend before 1st line of a file

     ruby -pe 'BEGIN {$prepend_txt = "-- Licence text --"}; puts $prepend_txt if $.==1' -i.back.`date +%Y-%m-%d_%T` file

* Append after last line of a file

    IN_FILE=file ruby -e 'File.open(ENV["IN_FILE"], "a") {|f| f.write("--Credit --\n") }'

    ruby -pe 'gsub(/$\n/, "\n--Credit --\n") if ARGF.eof?' -i.back.`date +%Y-%m-%d_%T` file





