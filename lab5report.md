# less Examples
## Example 1: 
Using less -N [file]

This command outputs the line number on the left of each line, as seen below. This could be useful if you are searching through a file and want to track where you are.

<pre><code>
% less -N government/Media/Court_Keeps_Judge_From.txt
      1 
      2 
      3 
      4 
      5 Court Keeps Judge From Distributing Funds To Legal Aid Groups;
      6 Nixon Is Challenging His Authority To Spend Up To $750,000
      7 Virginia Young Post-Dispatch Jefferson City Bureau
      8 The Missouri Court of Appeals in St. Louis has blocked a judge's
      9 proposal to give as much as $750,000 to organizations that provide
     10 legal services for the poor.
     11 Attorney General Jay Nixon sought the order, which was granted
     12 Wednesday on an emergency basis. Nixon wanted to prevent Cole
     13 County Circuit Judge Thomas Brown III from distributing the funds
     14 as early as today.
     15 Nixon's office is challenging Brown's authority to spend the
     16 money. An Osage County judge who heard the dispute sided with Brown
     17 in September, but Nixon is appealing that decision. Wednesday's
     18 action bars Brown from transferring the money until the appeals
     19 court rules.
     20 The funds are part of about $2.75 million in interest that
     21 accrued in several state cases brought on behalf of consumers. The
     22 attorney general contends that the money belongs in the state's
     23 unclaimed property fund.
:
</code></pre>

## Example 2:
Using less -p[searchTerm] [file]

This finds the keyword that's directly after the -p. In my case, I looked for the term "court", and the output highlights every instance of "court" i in the provided file. This could be useful if you're trying to see all instances where a method is called for example.

<pre><code>
% less -pcourt government/Media/Court_Keeps_Judge_From.txt

The funds are part of about $2.75 million in interest that
accrued in several state cases brought on behalf of consumers. The
attorney general contends that the money belongs in the state's
unclaimed property fund.
Brown decided last week to designate some of the money for four
legal aid organizations, including the St. Louis-based Legal
Services of Eastern Missouri.
Nixon's spokeswoman, Mary Still, said the emergency order "was
needed to keep the money in safekeeping, so it could be distributed
to its rightful owners." While legal aid is a worthy cause, Nixon
"doesn't believe the judge has legal authority to give the money to
that cause," she said.
Brown's attorney, Dale Doerhoff, said Wednesday's action was
unnecessary because Brown never intended to distribute the money
until all legal questions about his authority were resolved.
The money is left over from cases involving utility bill
overpayments and an insurance company insolvency. Brown and Cole
County Circuit Judge Byron Kinder used some of the money to remodel
the Cole County Courthouse and to pay additional salaries to
courthouse secretaries.
</code></pre>
## Example 3:
Using less -s [file]

This command eliminates empty lines. As you can see in the output below, this has eliminated some empty lines in the inputted file.

This is pretty helpful since it can be a lot quicker than manually deleting empty lines. 

<pre><code>
% less -s government/Media Court_Keeps_Judge_From.txt

action bars Brown from transferring the money until the appeals
court rules.
The funds are part of about $2.75 million in interest that
accrued in several state cases brought on behalf of consumers. The
attorney general contends that the money belongs in the state's
unclaimed property fund.
Brown decided last week to designate some of the money for four
legal aid organizations, including the St. Louis-based Legal
Services of Eastern Missouri.
Nixon's spokeswoman, Mary Still, said the emergency order "was
needed to keep the money in safekeeping, so it could be distributed
to its rightful owners." While legal aid is a worthy cause, Nixon
"doesn't believe the judge has legal authority to give the money to
that cause," she said.
Brown's attorney, Dale Doerhoff, said Wednesday's action was
unnecessary because Brown never intended to distribute the money
until all legal questions about his authority were resolved.
The money is left over from cases involving utility bill
overpayments and an insurance company insolvency. Brown and Cole
County Circuit Judge Byron Kinder used some of the money to remodel
the Cole County Courthouse and to pay additional salaries to
courthouse secretaries.
</code></pre>

# find Examples:
## Example 1:

Using find [path] -empty


This will find empty folders and files in the specificed directory.
<pre><code>
% find ./911report -empty
</code></pre>
This doesn't output anything since there are no empty files/folders in this directory. This could be useful if you wanted to eliminate redundant folders.

## Example 2: 

Using find [path] -name [type of file]

This method is very useful in finding the names of files of a specific type. For example, I inputted 

<pre><code>
% find ./911report -name "*.txt" 
</code></pre>
This should provide me with all the files of type .txt:

<pre><code>
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-13.1.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-3.txt
./911report/chapter-2.txt
./911report/chapter-1.txt
./911report/chapter-5.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-9.txt
./911report/chapter-8.txt
./911report/preface.txt
./911report/chapter-12.txt
./911report/chapter-10.txt
./911report/chapter-11.txt
</code></pre>

## Example 3: 
Using find [directory] -newer [file]

This will search through a directory and return files that are newer than the file being compared to. This can be useful if you want to know when certain files were edited. 

<pre><code>
% find ./911report -newer "./911report/chapter-1.txt" 
</code></pre>

This returns nothing because all the files were created at the same time, but in other cases this would return something.

# grep Examples:

## Example 1: 

Using grep - c [search term] [file]

This command finds the amounts of lines that contain the search term in the specified file. This can be useful if there are a lot of instances of a specific word and you don't want to count manually.
<pre><code>
Alcohol_Problems % grep -c "alcohol" Session2-PDF.txt
97
</code></pre>
This returns 97 since there are 97 lines where the word "alcohol" appears.

## Example 2: 

Using grep -w [search term] [file]

This command returns the lines which include the search term in the specified file. 

This can be useful if you need to filter out lines that do have a certain word and those that do not. 
<pre><code>
Alcohol_Problems % grep -w "care" Session2-PDF.txt


the first step in a process of care.
screening test to an already lengthy list of clinical care duties.
identify only 50% of acutely intoxicated patients.13 Primary care
asked. Cyr reported that a single question in a primary care
Most existing screens were developed for primary care settings
a brief screening tool for primary care providers to detect alcohol
primary care physicians ask an opening question-"Do you drink
primary care setting. For at-risk, hazardous, or harmful drinking,
screening mainly in primary care settings. CAGE, AUDIT, and TWEAK
recommended by NIAAA for primary care should be compared with other
ED patient care should be improved by implementing alcohol
Most EDs provide very limited alcohol services. When care is
screening in an ambulatory care setting. J Stud Alcohol
consumption and related problems among primary health care
problems in primary care: a systematic review. Arch Intern Med
M. Prevalence and recognition of alcohol abuse in a primary care
alcoholism in primary health care: compared efficacy of different
brief intervention among heavy drinkers in primary health care.
primary care. Arch Fam Med 1995;4:211-9.
mental disorders in primary care. J Gen Intern Med.
</code></pre>

## Example 3:

Using grep -n [search term] [file]

This command is very similar to the one in example 2. It finds lines containing the search term in the specified file and returns them. However, this differs from the previous command in that it also shows you the line number of those returned lines.

This is quite useful in finding lines containing a specific search term and then tracing them back to where they are in the original file.

<pre><code>
Alcohol_Problems % grep -n "care" Session2-PDF.txt


20:the first step in a process of care.
24:We must be careful when interpreting the results of studies, and in
103:screening test to an already lengthy list of clinical care duties.
143:identify only 50% of acutely intoxicated patients.13 Primary care
158:asked. Cyr reported that a single question in a primary care
165:Most existing screens were developed for primary care settings
167:a brief screening tool for primary care providers to detect alcohol
215:primary care physicians ask an opening question-"Do you drink
233:primary care setting. For at-risk, hazardous, or harmful drinking,
251:screening mainly in primary care settings. CAGE, AUDIT, and TWEAK
257:among white women. We must be careful not to employ screening
338:recommended by NIAAA for primary care should be compared with other
401:ED patient care should be improved by implementing alcohol
405:Most EDs provide very limited alcohol services. When care is
484:screening in an ambulatory care setting. J Stud Alcohol
518:consumption and related problems among primary health care
540:problems in primary care: a systematic review. Arch Intern Med
561:M. Prevalence and recognition of alcohol abuse in a primary care
564:alcoholism in primary health care: compared efficacy of different
577:brief intervention among heavy drinkers in primary health care.
585:primary care. Arch Fam Med 1995;4:211-9.
587:mental disorders in primary care. J Gen Intern Med.
</code></pre>