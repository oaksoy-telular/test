
a: --- a1 --- a2 --- a3---- a4
       |                | 
b:     b1 --- b2 --------


a = main line
b = branch from a
a4 = change from main (a1 to a3) + change from branch (b1 to b2).

I. To create b from a:
 1. define branch spec
  a. branchspec | new
   1. define name
   2. define description
   3. define source and destination
    i.e. //tg/perforcetest/a/... //tg/perforcetest/b/...
        (reads all files from branch to all file to)


 2. preview branch spec
  a. select created branch spec
  b. branchspec | Integrate Using <branch spec name>
  c. click preview

 observe:

Integrate preview: //tg/perforcetest/b/file.c#1 - branch/sync from //tg/perforcetest/a/file.c#1
Integrate preview: //tg/perforcetest/b/readme.txt#1 - branch/sync from //tg/perforcetest/a/readme.txt#1
Integrate preview completed


 3. create change list for branch spec
  a. select created branch spec
  b. branchspec | Integrate Using <branch spec name>
  c. click ok

  observe:

//tg/perforcetest/b/file.c#1 - branch/sync from //tg/perforcetest/a/file.c#1
//tg/perforcetest/b/readme.txt#1 - branch/sync from //tg/perforcetest/a/readme.txt#1
Opened 2 files for integrate

 changelist created for branched files.


 4. Submit change list to create branch

  submittal creates branch b within depot


II. Edit file for a3 and b2 changes


III. Merge changes from a and b.
 1. Select destination to merge into
 2. right click, select Integrate using Filespec
   a. define source filespec (branch b)
   b. select new changelist
   c. click ok

   Source Filespec: c:\tg\perforcetest\b\...
   Target Filespec: c:\tg\perforcetest\a\...

   observe: (with file.c changed)

//tg/perforcetest/a/file.c#3 - integrate from //tg/perforcetest/b/file.c#2
Opened 1 files for integrate

New files with change list added, opened for edit

 3. files that have changed in a and b need resolution (shown with exclaimation)
  a. right click changelist
  b. select Resolve File | Auto-resolve...
   1. select (*) all files in selected changelist for <Auto-Resolve>
   2. select (*) automatic or safe for <Resolve Type>
   3. click ok

  observe:

Diff chunks: 2 yours + 1 theirs + 0 both + 0 conflicting
//ny_wrk_111/tg/perforcetest/a/file.c - merge from //tg/perforcetest/b/file.c
1 files resolved
 
 4. Submit change list to complete merge







  



