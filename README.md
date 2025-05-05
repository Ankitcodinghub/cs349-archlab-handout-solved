# cs349-archlab-handout-solved
**TO GET THIS SOLUTION VISIT:** [CS349 Archlab-handout Solved](https://www.ankitcodinghub.com/product/cs349-archlab-handout-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;100094&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS349 Archlab-handout Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
1 Introduction

In this lab, you will learn about the design and implementation of a pipelined Y86-64 processor, optimizing both it and a benchmark program to maximize performance. You are allowed to make any semantics- preserving transformation to the benchmark program, or to make enhancements to the pipelined processor, or both. When you have completed the lab, you will have a keen appreciation for the interactions between code and hardware that affect the performance of your programs.

The lab is organized into three parts, each with its own handin. In Part A you will write some simple Y86-64 programs and become familiar with the Y86-64 tools. In Part B, you will extend the SEQ simulator with a new instruction. These two parts will prepare you for Part C, the heart of the lab, where you will optimize the Y86-64 benchmark program and the processor design.

2 Logistics

You will work on this lab alone.

Any clarifications and revisions to the assignment will be posted on the course Web page.

</div>
</div>
<div class="layoutArea">
<div class="column">
3

</div>
<div class="column">
Handout Instructions

SITE-SPECIFIC: Insert a paragraph here that explains how students should download

the archlab-handout.tar file.

1. Start by copying the file archlab-handout.tar to a (protected) directory in which you plan to do your work.

</div>
</div>
<div class="layoutArea">
<div class="column">
1

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
<ol start="2">
<li>Then give the command: tar xvf archlab-handout.tar. This will cause the following files to be unpacked into the directory: README, Makefile, sim.tar, archlab.pdf, and simguide.pdf.</li>
<li>Next, give the command tar xvf sim.tar. This will create the directory sim, which contains your personal copy of the Y86-64 tools. You will be doing all of your work inside this directory.</li>
<li>Finally, change to the sim directory and build the Y86-64 tools: unix&gt; cd sim
unix&gt; make clean; make
</li>
</ol>
4 PartA

You will be working in directory sim/misc in this part.

Your task is to write and simulate the following three Y86-64 programs. The required behavior of these programs is defined by the example C functions in examples.c. Be sure to put your name and ID in a comment at the beginning of each program. You can test your programs by first assemblying them with the program YAS and then running them with the instruction set simulator YIS.

In all of your Y86-64 functions, you should follow the x86-64 conventions for passing function arguments, using registers, and using the stack. This includes saving and restoring any callee-save registers that you use.

sum.ys: Iteratively sum linked list elements

Write a Y86-64 program sum.ys that iteratively sums the elements of a linked list. Your program should consist of some code that sets up the stack structure, invokes a function, and then halts. In this case, the function should be Y86-64 code for a function (sum list) that is functionally equivalent to the C sum list function in Figure 1. Test your program using the following three-element list:

<pre># Sample linked list
.align 8
ele1:
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
ele2:

ele3:

</div>
<div class="column">
<pre>.quad 0x00a
.quad ele2
</pre>
<pre>.quad 0x0b0
.quad ele3
</pre>
<pre>.quad 0xc00
.quad 0
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
1

2

3

4

5

6

7

8 9{

</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>/* linked list element */
typedef struct ELE {
</pre>
long val;

<pre>    struct ELE *next;
} *list_ptr;
</pre>
<pre>/* sum_list - Sum the elements of a linked list */
long sum_list(list_ptr ls)
</pre>
<pre>    long val = 0;
    while (ls) {
</pre>
<pre>        val += ls-&gt;val;
</pre>
<pre>        ls = ls-&gt;next;
    }
</pre>
return val; }

<pre>/* rsum_list - Recursive version of sum_list */
long rsum_list(list_ptr ls)
{
</pre>
<pre>    if (!ls)
        return 0;
</pre>
<pre>    else {
        long val = ls-&gt;val;
        long rest = rsum_list(ls-&gt;next);
        return val + rest;
</pre>
} }

<pre>/* copy_block - Copy src to dest and return xor checksum of src */
long copy_block(long *src, long *dest, long len)
{
</pre>
<pre>    long result = 0;
    while (len &gt; 0) {
</pre>
<pre>        long val = *src++;
        *dest++ = val;
        result ˆ= val;
        len--;
</pre>
}

<pre>    return result;
}
</pre>
Figure 1: C versions of the Y86-64 solution functions. See sim/misc/examples.c

</div>
</div>
<div class="layoutArea">
<div class="column">
3

</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="layoutArea">
<div class="column">
rsum.ys: Recursively sum linked list elements

Write a Y86-64 program rsum.ys that recursively sums the elements of a linked list. This code should be similar to the code in sum.ys, except that it should use a function rsum list that recursively sums a list of numbers, as shown with the C function rsum list in Figure 1. Test your program using the same three-element list you used for testing list.ys.

copy.ys: Copy a source block to a destination block

Write a program (copy.ys) that copies a block of words from one part of memory to another (non-

overlapping area) area of memory, computing the checksum (Xor) of all the words copied.

Your program should consist of code that sets up a stack frame, invokes a function copy block, and then halts. The function should be functionally equivalent to the C function copy block shown in Figure Figure 1. Test your program using the following three-element source and destination blocks:

<pre>.align 8
# Source block
src:
</pre>
<pre>        .quad 0x00a
        .quad 0x0b0
        .quad 0xc00
</pre>
<pre># Destination block
dest:
</pre>
<pre>        .quad 0x111
        .quad 0x222
        .quad 0x333
</pre>
5 PartB

You will be working in directory sim/seq in this part.

Your task in Part B is to extend the SEQ processor to support the iaddq, described in Homework problems 4.51 and 4.52. To add this instructions, you will modify the file seq-full.hcl, which implements the version of SEQ described in the CS:APP3e textbook. In addition, it contains declarations of some constants that you will need for your solution.

Your HCL file must begin with a header comment containing the following information: • Your name and ID.

• A description of the computations required for the iaddq instruction. Use the descriptions of irmovq and OPq in Figure 4.18 in the CS:APP3e text as a guide.

</div>
</div>
<div class="layoutArea">
<div class="column">
4

</div>
</div>
</div>
<div class="page" title="Page 5">
<div class="layoutArea">
<div class="column">
Building and Testing Your Solution

Once you have finished modifying the seq-full.hcl file, then you will need to build a new instance of the SEQ simulator (ssim) based on this HCL file, and then test it:

<ul>
<li>Building a new simulator. You can use make to build a new SEQ simulator: unix&gt; make VERSION=full
This builds a version of ssim that uses the control logic you specified in seq-full.hcl. To save typing, you can assign VERSION=full in the Makefile.
</li>
<li>Testing your solution on a simple Y86-64 program. For your initial testing, we recommend running simple programs such as asumi.yo (testing iaddq) in TTY mode, comparing the results against the ISA simulation:
unix&gt; ./ssim -t ../y86-code/asumi.yo

If the ISA test fails, then you should debug your implementation by single stepping the simulator in

GUI mode:

unix&gt; ./ssim -g ../y86-code/asumi.yo
</li>
<li>Retesting your solution using the benchmark programs. Once your simulator is able to correctly execute small programs, then you can automatically test it on the Y86-64 benchmark programs in ../y86-code:
unix&gt; (cd ../y86-code; make testssim)

This will run ssim on the benchmark programs and check for correctness by comparing the resulting processor state with the state from a high-level ISA simulation. Note that none of these programs test the added instructions. You are simply making sure that your solution did not inject errors for the original instructions. See file ../y86-code/README file for more details.
</li>
<li>Performing regression tests. Once you can execute the benchmark programs correctly, then you should run the extensive set of regression tests in ../ptest. To test everything except iaddq and leave:
unix&gt; (cd ../ptest; make SIM=../seq/ssim)

To test your implementation of iaddq:

unix&gt; (cd ../ptest; make SIM=../seq/ssim TFLAGS=-i)

For more information on the SEQ simulator refer to the handout CS:APP3e Guide to Y86-64 Processor Simulators (simguide.pdf).
</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
5

</div>
</div>
</div>
<div class="page" title="Page 6">
<div class="layoutArea">
<div class="column">
1

2

3

4

5 6{ 7

8

<pre> 9
10
11
12
13
14
15
16
17
18
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>/*
 * ncopy - copy src to dst, returning number of positive ints
 * contained in src array.
 */
</pre>
<pre>word_t ncopy(word_t *src, word_t *dst, word_t len)
</pre>
<pre>    word_t count = 0;
    word_t val;
</pre>
<pre>    while (len &gt; 0) {
        val = *src++;
        *dst++ = val;
</pre>
<pre>        if (val &gt; 0)
            count++;
</pre>
len–; }

</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>    return count;
}
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
6 PartC

</div>
</div>
<div class="layoutArea">
<div class="column">
Figure 2: C version of the ncopy function. See sim/pipe/ncopy.c.

</div>
</div>
<div class="layoutArea">
<div class="column">
You will be working in directory sim/pipe in this part.

The ncopy function in Figure 2 copies a len-element integer array src to a non-overlapping dst, re- turning a count of the number of positive integers contained in src. Figure 3 shows the baseline Y86-64 version of ncopy. The file pipe-full.hcl contains a copy of the HCL code for PIPE, along with a declaration of the constant value IIADDQ.

Your task in Part C is to modify ncopy.ys and pipe-full.hcl with the goal of making ncopy.ys run as fast as possible.

You will be handing in two files: pipe-full.hcl and ncopy.ys. Each file should begin with a header comment with the following information:

• Your name and ID.

• A high-level description of your code. In each case, describe how and why you modified your code.

Coding Rules

You are free to make any modifications you wish, with the following constraints:

• Your ncopy.ys function must work for arbitrary array sizes. You might be tempted to hardwire your solution for 64-element arrays by simply coding 64 copy instructions, but this would be a bad idea because we will be grading your solution based on its performance on arbitrary arrays.

</div>
</div>
<div class="layoutArea">
<div class="column">
6

</div>
</div>
</div>
<div class="page" title="Page 7">
<div class="layoutArea">
<div class="column">
1 ##################################################################

</div>
</div>
<div class="layoutArea">
<div class="column">
2 # 3 # 4# 5 # 6# 7 # 8#

<ol start="9">
<li>9 &nbsp;##################################################################</li>
<li>10 &nbsp;# Do not modify this portion</li>
<li>11 &nbsp;# Function prologue.</li>
<li>12 &nbsp;#%rdi=src,%rsi=dst,%rdx=len</li>
<li>13 &nbsp;ncopy:</li>
</ol>
14

<ol start="15">
<li>15 &nbsp;##################################################################</li>
<li>16 &nbsp;# You can modify this portion</li>
</ol>
</div>
</div>
<div class="layoutArea">
<div class="column">
17

18

19

20

21

22 Loop: 23

24

25

26

27

28 Npos: 29

</div>
<div class="column">
<pre># Loop header
xorq %rax,%rax
andq %rdx,%rdx
jle Done
</pre>
<pre>mrmovq (%rdi), %r10
rmmovq %r10, (%rsi)
andq %r10, %r10
jle Npos
</pre>
<pre>irmovq $1, %r10
addq %r10, %rax
irmovq $1, %r10
subq %r10, %rdx
irmovq $8, %r10
addq %r10, %rdi
addq %r10, %rsi
andq %rdx,%rdx
jg Loop
</pre>
</div>
<div class="column">
<pre># count = 0;
# len &lt;= 0?
# if so, goto Done:
</pre>
# read val from src…

# …and store it to dst #val&lt;=0?

# if so, goto Npos:

# count++

# len–

</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>ncopy.ys - Copy a src block of len words to dst.
Return the number of positive words (&gt;0) contained in src.
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>Include your name and ID here.
Describe how and why you modified the baseline code.
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
30 31 32 33 34

<ol start="35">
<li>35 &nbsp;##################################################################</li>
<li>36 &nbsp;# Do not modify the following section of code</li>
</ol>
</div>
</div>
<div class="layoutArea">
<div class="column">
# src++

# dst++

#len&gt;0?

# if so, goto Loop:

</div>
</div>
<div class="layoutArea">
<div class="column">
<ol start="37">
<li>37 &nbsp;# Function epilogue.</li>
<li>38 &nbsp;Done:</li>
<li>39 &nbsp;ret</li>
<li>40 &nbsp;##################################################################</li>
<li>41 &nbsp;# Keep the following label at the end of your function</li>
<li>42 &nbsp;End:
Figure 3: Baseline Y86-64 version of the ncopy function. See sim/pipe/ncopy.ys.
</li>
</ol>
</div>
</div>
<div class="layoutArea">
<div class="column">
7

</div>
</div>
</div>
<div class="page" title="Page 8">
<div class="layoutArea">
<div class="column">
<ul>
<li>Your ncopy.ys function must run correctly with YIS. By correctly, we mean that it must correctly copy the src block and return (in %rax) the correct number of positive integers.</li>
<li>The assembled version of your ncopy file must not be more than 1000 bytes long. You can check the length of any program with the ncopy function embedded using the provided script check-len.pl:
unix&gt; ./check-len.pl &lt; ncopy.yo
</li>
<li>Yourpipe-full.hclimplementationmustpasstheregressiontestsin../y86-codeand../ptest
(without the -i flag that tests iaddq).

Other than that, you are free to implement the iaddq instruction if you think that will help. You may
</li>
</ul>
make any semantics preserving transformations to the ncopy.ys function, such as reordering instruc- tions, replacing groups of instructions with single instructions, deleting some instructions, and adding other instructions. You may find it useful to read about loop unrolling in Section 5.8 of CS:APP3e.

Building and Running Your Solution

In order to test your solution, you will need to build a driver program that calls your ncopy function. We have provided you with the gen-driver.pl program that generates a driver program for arbitrary sized input arrays. For example, typing

unix&gt; make drivers

will construct the following two useful driver programs:

<ul>
<li>sdriver.yo:Asmalldriverprogramthattestsanncopyfunctiononsmallarrayswith4elements. If your solution is correct, then this program will halt with a value of 2 in register %rax after copying the src array.</li>
<li>ldriver.yo: A large driver program that tests an ncopy function on larger arrays with 63 ele- ments. If your solution is correct, then this program will halt with a value of 31 (0x1f) in register %rax after copying the src array.
Each time you modify your ncopy.ys program, you can rebuild the driver programs by typing unix&gt; make drivers

Each time you modify your pipe-full.hcl file, you can rebuild the simulator by typing unix&gt; make psim VERSION=full

If you want to rebuild the simulator and the driver programs, type
</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
unix&gt; make VERSION=full

</div>
</div>
<div class="layoutArea">
<div class="column">
8

</div>
</div>
</div>
<div class="page" title="Page 9">
<div class="layoutArea">
<div class="column">
To test your solution in GUI mode on a small 4-element array, type

unix&gt; ./psim -g sdriver.yo

To test your solution on a larger 63-element array, type

unix&gt; ./psim -g ldriver.yo

Once your simulator correctly runs your version of ncopy.ys on these two block lengths, you will want to perform the following additional tests:

• Testing your driver files on the ISA simulator. Make sure that your ncopy.ys function works prop- erly with YIS:

unix&gt; make drivers

unix&gt; ../misc/yis sdriver.yo

• TestingyourcodeonarangeofblocklengthswiththeISAsimulator.ThePerlscriptcorrectness.pl generates driver files with block lengths from 0 up to some limit (default 65), plus some larger sizes.

It simulates them (by default with YIS), and checks the results. It generates a report showing the status for each block length:

unix&gt; ./correctness.pl

This script generates test programs where the result count varies randomly from one run to another,

and so it provides a more stringent test than the standard drivers.

If you get incorrect results for some length K, you can generate a driver file for that length that includes checking code, and where the result varies randomly:

unix&gt; ./gen-driver.pl -f ncopy.ys -n K -rc &gt; driver.ys unix&gt; make driver.yo

unix&gt; ../misc/yis driver.yo

The program will end with register %rax having the following value:

0xaaaa : All tests pass.

0xbbbb : Incorrect count

0xcccc : Function ncopy is more than 1000 bytes long.

0xdddd : Some of the source data was not copied to its destination.

0xeeee : Some word just before or just after the destination region was corrupted.

• Testing your pipeline simulator on the benchmark programs. Once your simulator is able to cor- rectly execute sdriver.ys and ldriver.ys, you should test it against the Y86-64 benchmark programs in ../y86-code:

unix&gt; (cd ../y86-code; make testpsim) 9

</div>
</div>
</div>
<div class="page" title="Page 10">
<div class="layoutArea">
<div class="column">
This will run psim on the benchmark programs and compare results with YIS.

<ul>
<li>Testing your pipeline simulator with extensive regression tests. Once you can execute the benchmark programs correctly, then you should check it with the regression tests in ../ptest. For example, if your solution implements the iaddq instruction, then
unix&gt; (cd ../ptest; make SIM=../pipe/psim TFLAGS=-i)
</li>
<li>Testing your code on a range of block lengths with the pipeline simulator. Finally, you can run the
same code tests on the pipeline simulator that you did earlier with the ISA simulator

unix&gt; ./correctness.pl -p

7 Evaluation

The lab is worth 190 points: 30 points for Part A, 60 points for Part B, and 100 points for Part C.

Part A

Part A is worth 30 points, 10 points for each Y86-64 solution program. Each solution program will be eval- uated for correctness, including proper handling of the stack and registers, as well as functional equivalence with the example C functions in examples.c.

The programs sum.ys and rsum.ys will be considered correct if the graders do not spot any errors in them, and their respective sum list and rsum list functions return the sum 0xcba in register %rax.

The program copy.ys will be considered correct if the graders do not spot any errors in them, and the copy block function returns the sum 0xcba in register %rax, copies the three 64-bit values 0x00a, 0x0b, and 0xc to the 24 bytes beginning at address dest, and does not corrupt other memory locations.

Part B

This part of the lab is worth 35 points:

<ul>
<li>10 points for your description of the computations required for the iaddq instruction.</li>
<li>10 points for passing the benchmark regression tests in y86-code, to verify that your simulator still correctly executes the benchmark suite.</li>
<li>15 points for passing the regression tests in ptest for iaddq. Part C
This part of the Lab is worth 100 points: You will not receive any credit if either your code for ncopy.ys or your modified simulator fails any of the tests described earlier.
</li>
</ul>
</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
10

</div>
</div>
</div>
<div class="page" title="Page 11">
<div class="layoutArea">
<div class="column">
8

</div>
<div class="column">
<ul>
<li>20 points each for your descriptions in the headers of ncopy.ys and pipe-full.hcl and the quality of these implementations.</li>
<li>60 points for performance. To receive credit here, your solution must be correct, as defined earlier. That is, ncopy runs correctly with YIS, and pipe-full.hcl passes all tests in y86-code and ptest.
We will express the performance of your function in units of cycles per element (CPE). That is, if the simulated code requires C cycles to copy a block of N elements, then the CPE is C/N. The PIPE simulator displays the total number of cycles required to complete the program. The baseline version of the ncopy function running on the standard PIPE simulator with a large 63-element array requires 897 cycles to copy 63 elements, for a CPE of 897/63 = 14.24.

Since some cycles are used to set up the call to ncopy and to set up the loop within ncopy, you will find that you will get different values of the CPE for different block lengths (generally the CPE will drop as N increases). We will therefore evaluate the performance of your function by computing the average of the CPEs for blocks ranging from 1 to 64 elements. You can use the Perl script benchmark.pl in the pipe directory to run simulations of your ncopy.ys code over a range of block lengths and compute the average CPE. Simply run the command

unix&gt; ./benchmark.pl

to see what happens. For example, the baseline version of the ncopy function has CPE values ranging between 29.00 and 14.27, with an average of 15.18. Note that this Perl script does not check for the correctness of the answer. Use the script correctness.pl for this.

You should be able to achieve an average CPE of less than 9.00. Our best version averages 7.48. If your average CPE is c, then your score S for this portion of the lab will be:

 0, c&gt;10.5

S = 20·(10.5−c), 7.50≤c≤10.50  60, c&lt;7.50

By default, benchmark.pl and correctness.pl compile and test ncopy.ys. Use the -f argument to specify a different file name. The -h flag gives a complete list of the command line arguments.

Handin Instructions

SITE-SPECIFIC: Insert a description that explains how students should hand in the three parts of the lab. Here is the description we use at CMU.

• You will be handing in three sets of files:

– Part A: sum.ys, rsum.ys, and copy.ys. – Part B: seq-full.hcl.
</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
11

</div>
</div>
</div>
<div class="page" title="Page 12">
<div class="layoutArea">
<div class="column">
– Part C: ncopy.ys and pipe-full.hcl.

<ul>
<li>Make sure you have included your name and ID in a comment at the top of each of your handin files.</li>
<li>To handin your files for part X, go to your archlab-handout directory and type:
unix&gt; make handin-partX TEAM=teamname

where X is a, b, or c, and where teamname is your ID. For example, to handin Part A:

unix&gt; make handin-parta TEAM=teamname
</li>
<li>After the handin, if you discover a mistake and want to submit a revised copy, type
unix make handin-partX TEAM=teamname VERSION=2 Keep incrementing the version number with each submission.
</li>
<li>You can verify your handin by looking in CLASSDIR/archlab/handin-partX
You have list and insert permissions in this directory, but no read or write permissions.

9 Hints
</li>
</ul>
<ul>
<li>By design, both sdriver.yo and ldriver.yo are small enough to debug with in GUI mode. We find it easiest to debug in GUI mode, and suggest that you use it.</li>
<li>If you running in GUI mode on a Unix server, make sure that you have initialized the DISPLAY environment variable:
unix&gt; setenv DISPLAY myhost.edu:0
</li>
<li>With some X servers, the “Program Code” window begins life as a closed icon when you run psim
or ssim in GUI mode. Simply click on the icon to expand the window.
</li>
<li>With some Microsoft Windows-based X servers, the “Memory Contents” window will not automati-
cally resize itself. You’ll need to resize the window by hand.
</li>
<li>The psim and ssim simulators terminate with a segmentation fault if you ask them to execute a file that is not a valid Y86-64 object file.</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
12

</div>
</div>
</div>
