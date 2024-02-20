Notes
https://www.theodinproject.com/lessons/foundations-command-line-basics 

    Knowledge Check
        What is the command line?
            it's the matrix...a way to interface with the OS outside of GUI-land
        How do you open the command line on your computer?
            via Visual Studio Code
            or opening Terminal on the Mac 
                via 
                    [ctrl]+[space],
                    enter 'iterm',
                    hit [enter]
        How can you navigate to a particular directory?
        Where will cd on its own navigate you to?
        Where will cd .. navigate you to?
        How do you display the name of the directory you are currently in?
        How do you display the contents of the directory you are currently in?
        How do you create a new directory?
        How do you create a new file?
        How do you destroy a directory or file?
        How do you rename a directory or file?
    Assignments
    https://www.theodinproject.com/lessons/foundations-command-line-basics#assignment
        2 
            With your newly discovered CLI super powers, practice creating a folder and 
            a few files using the mkdir, touch, and cd commands introduced in the previous 
            step. As an example, a basic website might have a main index.html file, 
            a CSS stylesheet file called style.css, and a folder for images. 
            
            Think about how you could create these files with the commands and 
            put it into practice!

        1
            The Unix Shell course/Sections
                Download files
                Introducing the Shell
                Navigating Files and Directories
                Working With Files and Directories
                Pipes and Filters 
            finished 2/14
    Notes
        [tab]
            tab completion is a thing 
        ~
            'the current user's home directory
        ..
            'the directory containing this one'
        |
            pass data to another command
                sort -n lengths.txt | head -n 1
                    sorts lengths.txt numerically, then passes the output to head -n 1 (which gets/outputs the first line (-n 1) of file)
            more fun
                wc -l *.pdb | sort -n | head -n 1
        &&
            run multiple commands
                git add . && git commit -m 'wowzers' && git push       
        >
            send output to file
                wc -1 *.pdb > lengths.txt
        cat details.txt
            displays contents of file to the screen
        cd
            'change directory'
            cd /Users/chris/Desktop
            cd..
                go to parent
        clear
            clears terminal
        cp quotes.txt thesis/quotations.txt 
            copies file quotes.txt into subdir thesis
            and then renames it to quotations.txt
        cp quotes.txt thesis/quotations.txt
            copies file to subdir and renames it
        cp creatures/minotaur.dat creatures/unicorn.dat backup/
            (multiple file args, destination as last arg)
        cut
            cut -d , -f 2 animals.csv
                -d ,
                    specifies 'comma delimiter'  (default is tab delimiter)
                -f 2
                    pic the second column of each row
        echo hello > file_01.txt
            replaces contents of file with the word 'hello'
        echo hello >> file_01.txt
            adds 'hello' on a new line at the end of the contents of file file_01.txt
        head -n 3 animals.csv > animals-subset.csv
            adds the first three lines of the former file into new lines in the latter file 
            also 
            tail -n 2 animals.csv >> animals-subset.csv
                adds the last two lines of the former file into new lines in the latter file 
        ls 
            list dir contents
            ls --help for more info, or
            man ls for more info

            -F adds markers to indicate 
                / a directory
                @ a link
                * an executable
                drills down to list all subdirectories and their contents
            ls -s 
                will display the size of files and directories alongside the names
            ls -S 
                will sort the files and directories by size
            ls *.txt
                lists all files in curent dir with ext .txt
            ls ????me.txt
                (directory contains readme.txt and readmeat.txt)
                lists files that match wildcard pattern (readme.txt, but not readmeat.txt)
            examples
                -h -l
                    a list with more deets
                ls -t -r -l sorted reverse order by last mod date
                ls -F Automator
                    lists contents of directory automator
                ls -F -a
                    -a means 'include hidden files' ah ha!
        man ls
            ls help manual
                navigate with 
                    up and down arrows
                    page up and down via B and Spacebar
                    /blarg searches for string "blarg"
                        toggle multiple hits with N and Shift+N
                    q quit
        mkdir thesis
            makes an empty directory named 'thesis' (of course)
        mv draft.txt quotes.txt
            renames file draft.txt to quotes.txt                
        mv child_dir/quotes.txt .
            (assumes that child_dir is a child of the current dir and that child_dir contains file quotes.txt)
            moves file found in child_dir\quotes.txt to the dir that you are in
        mkdir beef chicken fish
            makes three empty directories named beef, chicken and fish
        nano newfile.txt
            creates a new file if it doesn't exist (then opens in nano)
            or if file exists, opens it in nano
            navigation
        pwd
            displays current dir
        rm newfile.txt
            deletes the file
        rm -r dir_name
            deletes files in directory dir_name, then deletes the directory
        sort
            sort -n numbers.txt
                outputs numerical sorting of the lines of file numbers.txt  
            sort -n numbers.txt > sorted_numbers.txt
                writes numerical sorting of the lines of file numbers.txt to file sorted_numbers.txt
            cut -d , -f 2 animals.csv | sort | uniq
                sorts the output of animals.csv
        tail
            see 'head'
        touch newfile.txt
            creates a new file if it doesn't exist (then opens in nano)
            or if file exists, opens it in nano
            navigation
        uniq
            cut -d , -f 2 animals.csv | sort | uniq
                only displays unique output        
        wc filename.txt
            returns a count of lines, words and characters found in filename.txt
        wc *.txt
            returns counts for all .txt files in current dir
        wc -l *.txt
            returns letter count for all .txt files in current dir
        wc -w *.txt
            returns word count for all .txt files in current dir
        wc -c *.txt
            returns character count for all .txt files in current dir
        wc -l *.txt > details.txt
            writes command output to file details.txt