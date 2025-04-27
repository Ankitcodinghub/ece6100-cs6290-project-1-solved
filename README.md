# ece6100-cs6290-project-1-solved
**TO GET THIS SOLUTION VISIT:** [ECE6100_CS6290 Project 1 Solved](https://www.ankitcodinghub.com/product/ece6100_cs6290-cs-4-6290-ece-4-6100-spring-2024-solved-2/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;123983&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;4&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (4 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;ECE6100_CS6290  Project 1 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

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
            5/5 - (4 votes)    </div>
    </div>
1 Changelog

Ver sion 1.1: 2024- 02- 01: Sec tion 4.1 change L1 as so cia tiv ity re stric tion from SL1 ≥ 1 to

SL1 ≥ 0. All files from the new tar ball ex cept for cachesim.cpp have changed. Clar ified

•

grad sec tion re quire ments.

2 Rules

• This is a tough assignment that requires a good understanding of concepts before you can start writing code. Make sure to start early.

• Read the entire document before starting. Critical pieces of information and hints might be provided along the way.

• Unfortunately, experience has shown that there is a high chance that errors in the project description will be found and corrected after its release. It is your responsibility to check for updates on Canvas, and download updates if any.

• Make sure that all your code is written according to C11 or C++20 standards, using only the standard libraries.

3 Background

3.1 Prefetcher (+1 and Strided)

In this project we will use two prefetching schemes. The first one being a simple +1 Prefetcher and the second one being a Strided Prefetcher. Since the minimum unit the Prefetcher can fetch is a block, we only use the block address and ignore the block offset. Where “block address” is the concatenation of the tag and the index.

+1 Prefetcher: On a miss on block at block address X, if the next block (block at block address (X + 1)) is not in the cache, prefetch that block and insert it into the L2 cache. Prefetch (X + 1) only after inserting block X into the cache.

Strided Prefetcher: On a miss on a block at block address X, then on a block at block address Y , prefetch the block at block address Y +k where k = Y −X, if block at address Y + k is not in the cache. k is the difference between the current miss and the previous. Prefetch (Y + k) only after the block at block Y is inserted into the cache.

3.1.1 Insertion Policies (MIP and LIP)

In this project, we will consider two cache insertion policies when dealing with prefetching. The first is the standard insertion policy used in LRU replacement, which we call “MIP” for clarity:

MRU Insertion Policy (MIP): The MRU insertion policy means that new blocks are inserted in the MRU position. MRU insertion policy is originally defined only under the LRU replacement policy. For this project, we extend the definition of MIP under the LFU replacement policy. In this project, we define the MIP under LFU as setting the MRU bit of a block and clear other the MRU bit of every other block in the same set.

LRU Insertion Policy (LIP):

Designed for L2 caches to avoid thrashing on workloads with low temporal locality, LIP inserts all new blocks at the LRU position. Similarly, for this project, we define of LIP under the LFU replacement policy. We define LIP under LFU as clearing the MRU bit of the inserted block and leaving the MRU bit of other blocks in the set unmodified.

4 Simulator Specifications

In this project, you will build a simulator with a write-back, write-allocate L1 cache, and a write through, write-no-allocate L2 cache. Your simulator will receive a series of memory accesses from the CPU in a provided trace and must print some final statistics before exiting.

4.1 Simulator Configuration

Both the L1 and L2 caches should implement LRU replacement (for everyone) and LFU replacement (for students in 6100 &amp; 6290). The L1 cache follows the write-back, writeallocate write strategy. The L2 cache shares the L1 block size (B parameter) and follows the write-through, write-no-allocate write strategy. The system uses 64-bit addresses.

The L1 cache in your simulator will have the following configuration knobs:

• -c &lt; CL1 &gt;: A total size of 2CL1 bytes

• -b &lt; B &gt;: Block size of 2B bytes. This will also be the block size used for the L2 cache Restriction: The block size must be reasonable: 5 ≤ B ≤ 7

• -s &lt; SL1 &gt;: 2SL1-way associativity

Restriction: SL1 ≥ 1 0

The L2 cache in your simulator will have the following configuration knobs:

• -D: if this flag is supplied, the L2 cache is Disabled, it is enabled otherwise

• -C &lt; CL2 &gt;: A total size of 2CL2 bytes

Restriction: The size of the L2 cache must be strictly greater than the size of the L1 cache (CL2 &gt; CL1)

• -S &lt; SL2 &gt;: 2SL2-way associativity

Restriction: The associativity of the L2 cache must be greater than the associativity of the L1 cache (SL2 &gt; SL1)

Restriction: The L2 CL2 − SL2 must be greater than the L1 CL1 − SL1

• -P &lt; 0,1,2 &gt;: Sets the type of prefetcher to use

– 0: Disable prefetcher

– 1: Use +1 prefetcher Everyone

– 2: Use Strided Prefetcher students in 6100 &amp; 6290

• -I &lt;MIP, LIP&gt;: Prefetcher Insertion Policy

The following parameters apply to the entire simulation:

• -r &lt;LRU, LFU&gt;: Replacement policy for both caches: LRU (Everyone) or LFU (LFU is for students in 6100 &amp; 6290)

• -f &lt;Filename&gt;: The filename/path for the trace to execute

4.2 Simulator Semantics

4.2.1 L1 And L2 Obliviousness

In this project, the L1 cache does not know about the L2 cache, and vice versa. The bus connecting L1 to L2 is the width of an L1 cache block. Effectively, the L1 cache believes it is talking to memory, and the L2 cache believes it is talking to the CPU. For example, the L2 cache sees a write-back from L1 as a write to L2. So even during writebacks from L1, your L2 cache simulation code should increment L2 hit/miss statistics counters. Also, when performing a write to L2, if the block is present in L2 already, that block should be moved to the MRU position. (If the written block is not present in L2, do not add it, because L2 is write-through and write-no-allocate.) The L2 cache is write-through, meaning that the values in the L2 cache are always in sync with values in memory. Note that a write miss in L1 will first read the block from L2 and then update the L1 copy with the write.

4.2.2 Prefetching

Prefetching in the cache system is a trick that uses spatial/sequential locality to try to predict what blocks might be needed in the future. The main two types of prefetching schemes that we are going to implement in this cache system are the +1 prefetch and the strided prefetch.

+1 Prefetching

On an L2 cache read miss, we fetch the missing block from memory, but also fetch the next block in memory and bring it into the cache. If the next block is already in cache, we skip the prefetch.

Strided Prefetching (for students in 6100 &amp; 6290)

4.2.3 LRU Replacement and Tracking

One possible way to implement the LRU Replacement Policy is to use timestamp counters. We strongly recommend using timestamps to implement LRU tracking for this project as it follows the same logic of our implementation. To use this implementation, you need to keep track of the counter value where a certain block has been used and update it every time that block is used. This needs to be done per cache as there is possible cases where the LRU is different in the L1 cache and in the L2 cache. When it comes to evict a block, simply look through the timestamps associated with each block and evict the one with the farthest back (smallest) timestamp.

Here is how you will use and manage the timestamp counter.

• First, you initialize the cache’s timestamp counter to the value 2(C−B+1). • In cases where the block of current access or the block you want to prefetch is already in the cache:

– If the block of current access is already in cache, you set the timestamp of the block to the current value of the timestamp counter. This acts like setting the block to most recently used. After access, you increment the timestamp counter by 1.

– For MIP, you set the timestamp of the newly installed block to the current value of the timestamp counter. After insertion, you increment the timestamp counter by 1.

– For LIP, you set the timestamp of the newly installed block to lowest − 1. After insertion, you increment the timestamp counter by 1. We define lowest as the smallest timestamp of all valid blocks in the set you want to install a new block into. If there is no valid block in the set before insertion, lowest is undefined. In this case where lowest is undefined, you set the timestamp of the newly installed block to current value of the timestamp counter.

4.2.4 LFU Replacement and Tracking

Note: Implementation of LFU Replacement Policy is for students in 6100 &amp; 6290. To implement the LFU Replacement Policy, you must keep a counter of how many times a certain block is used and refer to the counter when deciding which block to evict. However, the naive LFU Replacement Policy has one huge fatal flaw. Imagine missing on a block with a full cache. When you bring in that new block, you replace the LFU, but now that new block is most likely the LFU. If the next access is also a miss, then that next block will replace the block that you just brought in. This is very inefficient and goes against temporal locality, therefore we will use the MRU bit to prevent this case. The MRU bit serves as a way to prevent a block from being evicted. When it comes to evict a block, simply check each counter for each block and evict the one with the lowest counter with the restriction that you do not evict the block that has the MRU bit set. In the cases where multiple blocks are equal in terms of frequency of use, break the tie by choosing to evict the block with the smallest tag.

We track LFU status by having a “use” counter for each block that counts how many times it has been used and a MRU bit for each block that tells us if it is the MRU block in the set. • In cases where the block of current access or the block you want to prefetch is already in the cache:

– If the block of current access is already in cache, you set the MRU bit of the block and clear the MRU bit of every other block in the same set. After access, you increment the block’s “use” counter by 1.

– For MIP, you set the MRU bit of this new block and clear the MRU bit of every other block in the same set.

– For LIP, you clear the MRU bit of this new block. You leave the MRU bit of the other blocks in the set unmodified.

• If the newly installed block is the block of current access, set the “use” counter to 1. If the newly installed block is the block you prefetched, set the “use” counter to 0.

4.2.5 Serial Checks

1. Check L1 cache

2. Check L2 cache

However, your simulator should increment hit/miss counters for the L2 cache only when L1 has missed. Similarly, blocks in L2 should not move into the MRU position for an access unless the L1 cache missed.

4.2.6 Do Not Writeback Before L2 Read

When the L1 cache misses, please have the L1 cache perform a read from L2 before you write back a dirty victim block to L2. Otherwise, if the block written back and the requested block share an L2 set, their positions in the LRU queue for their L2 set could be swapped compared to the expected behavior.

4.2.7 Disabling Caches

For simplicity, when the L2 cache is disabled, it should act as an zero-sized write-through cache: it should miss on every read, and send all writes directly to DRAM. L2 statistics still need to be updated and printed in this case. However, if the L2 cache is disabled, please set its hit time (HT) to zero.

4.3 Simulator Statistics

Your simulator will calculate and output the following statistics:

• Overall statistics:

– Reads (reads): Total number of cache reads – Writes (writes): Total number of cache writes

• L1 statistics:

– L1 accesses (accesses l1): Number of times L1 cache was accessed – L1 hits (hits l1): Total number of L1 hits.

– L1 misses (misses l1): Total number of L1 misses.

– L1 hit ratio (hit ratio l1): Hit ratio for L1, calculated using the first three L1 stats above.

– L1 miss ratio (miss ratio l1): Miss ratio for L1, calculated using the first three L1 stats above.

– L1 AAT (avg access time l1): See Section 4.3.1

• L2 statistics:

– L2 reads (reads l2): Number of times the L2 cache received a read request. This stat should not be touched unless there was L1 read miss

– L2 writes (writes l2): Number of times the L2 cache received a write request. This stat should not be touched unless there was a write-back from L1 cache

– L2 read hits (read hits l2): Total number of L2 read hits. This stat should not be touched unless there was an L1 cache miss

– L2 read misses (read misses l2): Total number of L2 read misses. This stat should not be touched unless there was an L1 cache miss

– L2 prefetches (prefetches l2): Total number of L2 prefetches. This stat should not be touched unless the block you want to prefetch is not in the cache at the time you want to bring it in.

– L2 read hit ratio (read hit ratio l2): Read hit ratio for L2, calculated using earlier L2 read stats.

– L2 read miss ratio (read miss ratio l2): Read miss ratio for L2, calculated using earlier L2 read stats.

– L2 AAT (avg access time l2): See Section 4.3.1

4.3.1 Average Access Time

For the purposes of average access time (AAT) calculation, we assume that:

• For L1, hit time is k0 + (k1 × (CL1 − BL1 − SL1)) + k2 × (max(3,SL1) − 3)

– k0 = 1ns

– k1 = 0.15ns

– k2 = 0.15ns

• For L2, hit time is k3 + (k4 × (CL2 − BL2 − SL2)) + k5 × (max(3,SL2) − 3)

– k3 = 4ns

– k4 = 0.3ns

– k5 = 0.3ns

• The time to access DRAM is 100ns

The provided header file, cachesim.hpp, includes constants for these values. These values are in nanoseconds. Please also provide your answer in nanoseconds.

AATL1 = HTL1 + MRL1 × MPL1

where the hit time HTL1 is as calculated above, and MRL1 is the L1 miss ratio (miss ratio l1).

When computing the AAT for the L2 cache, which is write-through and write-no-allocate, use the L2 read miss ratio (read miss ratio l2) as the miss ratio in the AAT equation.

5 Implementation Details

We included a driver, cachesim driver.cpp, which parses arguments, reads a trace from standard input, and invokes your sim access() function in cachesim.cpp for each memory access in the trace. The driver takes a flag for each of the knobs described in Section 4.1; run ./cachesim -h to see the list of options.

The provided cachesim.cpp template file also contains sim setup() and sim finish() functions you should complete for simulator setup and cleanup (including final stats calculations), respectively. By default, the provided ./run.sh script invokes the ./cachesim binary produced by linking cachesim driver.cpp with cachesim.cpp.

5.1 Docker Image

We have provided an Ubuntu 22.04 LTS Docker image for verifying that your code compiles and runs in the environment we expect — it is also useful if you do not have a Linux machine handy. To use it, install Docker (https://docs.docker.com/get-docker/) and extract the provided project tarball and run the 6290docker* script in the project tarball corresponding to your OS. That should open an 22.04 bash shell where the project folder is mounted as a volume at the current directory in the container, allowing you to run whatever commands you want, such as make, gdb, valgrind, ./cachesim, etc.

Note: Using this Docker image is not required if you have a Linux system available and just want to make sure your code compiles on 22.04. We will set up a Gradescope autograder that automatically verifies we can successfully compile your submission.

6 Validation Requirements

We have provided six memory traces in the traces/ directory of the provided project tarball. Validation outputs for the default simulator configuration for each of these traces are provided in the ref outs/ directory. There are also validation outputs for gcc under the default configuration except with only L1 (-D), L1 and L2 with prefetcher disabled (-P 0). Given these configurations, the output of your code must match these reference outputs byte-for-byte! We have included a script to compare the output of your simulator to these reference outputs using make validate undergrad (for students in 4100 &amp; 4290) and make validate grad (for students in 6100 &amp; 6290).

6.1 Debug Traces

Debugging this project can be difficult, particularly when looking only at final statistics. We have provided some verbose debug traces for you that correspond to the reference traces. To motivate you to use them, part of your grade will depend on you implementing matching debug traces in your own code (see Section 9). Please see the debug outs/README.txt for more information.

Note that your debugging statements should only print when a special DEBUG flag is set. Otherwise, it will slow down your implementation and potentially cause issues during grading. To make the debugging statements conditional, use the following code:

#ifdef DEBUG

// Your debug statement here

#endif

To see your debugging statements print when you test your implementation, add DEBUG=1 to the make command.

7 Experiments

Once you have your simulator working, you should find an optimal cache configuration for each of the six traces that meets the following constraints:

1. Configuration should respect all the restrictions mentioned in Section 4.1

2. The L2 data store is 128KiB (C = 17)

3. The L1 data store is 32KiB (C = 15)

An optimal cache configuration would have the lowest average access time, while minimizing metadata/tag storage. Identify points of diminishing returns in terms of cache parameters (C, B, S). Consider that highly associative caches can use substantially more area and power. Include any rationale, quantitatively or qualitatively, to justify your decisions.

In your report you must provide, in addition to the cache configuration, the total size of any associated metadata required to build the cache for your recommended configuration(s), except for the LRU/LFU tracking metadata.

You should submit a report in PDF format (inside your submission tarball) in which you describe your methodology, rationale, and results.

8 What to Submit to Gradescope

Please submit your project to Gradescope as a tarball containing the your experiments writeup as a PDF, as well as everything needed to build your project: the Makefile, the run.sh script, and all code files (including provided code). You can use the make submit target in the provided Makefile to generate your tarball for you. Please extract your submission tarball and check it before submitting!

We plan to enable a Gradescope autograder that will verify that your code compiles on 22.04 at submission time and test your implementation.

9 Grading

You will be evaluated on the following criterion:

+50: You turn in well commented significant code that compiles and runs but does not match the validation

+35: Your simulator completely matches the validation output

+10: You ran experiments and found the optimum configuration for the ‘experiments’ workload and presented sufficient evidence and reasoning

+5: You implement debug outputs as explained in Section 6.1. Your code is well formatted, commented and does not have any memory leaks! Check out the section on helpful tools

• Copy/share code from/with your fellow classmates or from people who might have taken this course in prior semesters.

• Publish your assignments on public repositories, github, etc, that are accessible to other students.

• Submit an assignment with code or text from an AI assistant (e.g., ChatGPT).

Anything you did not write in your assignment will be treated as an academic misconduct case. If you are unsure where the line is between collaborating with AI and copying AI, we recommend the following heuristics:

Heuristic 1: Never hit “Copy” within your conversation with an AI assistant. You can copy your own work into your own conversation, but do not copy anything from the conversation back into your assignment. Instead, use your interaction with the AI assistant as a learning experience, then let your assignment reflect your improved understanding.

Heuristic 2: Do not have your assignment and the AI agent open at the same time. Similar to the above, use your conversation with the AI as a learning experience, then close the interaction down, open your assignment, and let your assignment reflect your revised knowledge. This heuristic includes avoiding using AI directly integrated into your composition environment: just as you should not let a classmate write content or code directly into your submission, so also you should avoid using tools that directly add content to your submission.

Deviating from these heuristics does not automatically qualify as academic misconduct; however, following these heuristics essentially guarantees your collaboration will not cross the line into misconduct.

Appendix B – Helpful Tools

You might the following tools helpful: • gdb: The GNU debugger will prove invaluable when you eventually run into that segfault. The Makefile provided to you enables the debug flag which generates the required symbol table for gdb by default.

– To pass a trace on standard in (as cachesim expects) while running in gdb, you can invoke gdb with gdb ./cachesim and then run run &lt;cachesim args&gt; at the gdb prompt

• Valgrind: Valgrind is really useful for detecting memory leaks. Use the following command to track all leaks and errors:

valgrind –leak-check=full –show-leak-kinds=all –track-origins=yes

./cachesim &lt;cachesim args&gt;
