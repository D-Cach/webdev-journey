shell = the program that reads the commands you type and runs them. The terminal (or Git Bash's window) is just the box it runs inside — think of the terminal as the phone handset, and the shell as the person on the line who actually does what you ask. You use it for creating folders and pushing + committing files to your GitHub.

pwd = "print working directory". Tells you exactly what directory you are in.

ls = shows the files in the directory.

ls -a = shows all files including the hidden ones whose name starts with a dot (.).

ls -l = shows the details for each file in the directory.

cd = change directory. How you move between folders.

cd ~ = go to your home directory — a fixed location (e.g. /c/Users/dcach), not "the main folder."

cd .. = move up one level.

cd - = go back to the previous directory.

absolute paths = a full address to a folder, starting from the root (/). Works the same no matter where you currently are.

relative paths = a path written relative to your current folder — not the folder itself. Examples: notes/day1.md (down into notes), ../webdev (up one level, then into webdev).

. = current directory.

.. = parent directory (one level up).

mkdir = make directory or new folder.

touch = create an empty file.

mv = move — used for renaming files or moving files.

cp = copy. Plain cp only copies files — copying a folder needs cp -r.

rm = remove or delete a file.

rmdir = remove directory, but only if it is empty.

-r = recursive. Makes a command apply to a folder and everything inside it, all the way down. Used with rm to delete a non-empty folder, and with cp since plain cp refuses to copy folders at all.

Warning about using rm — deleted files don't go to the recycling bin. They're gone immediately.