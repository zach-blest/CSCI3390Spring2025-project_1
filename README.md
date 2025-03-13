Zach Blest: 31871610
Lukas Gearin: 25823070

Input: this_is_a_bitcoin_block_of_31871610_and_25823070

Question 1: 
k=2, n=100: xS=007d63460b271b83827b9e03a8f372bfc4caee046bfbe17c04f43e61711eaea6
Time Elapsed=5 seconds

k=3, n=100:
xS=0002b34ee0ff883a2689e7067a163d1e2c3d0e82c13a500e47a2857af7b393c2
Time Elapsed=5 seconds

k=4, n=20,000:
xS=0000c912ebbe6d1fc5d47830ed4afac5545433310c3582b4ac9f8f47d8f1047e
Time Elapsed=5 seconds

k=5, n=550,000
xS=000001a2155529194cd0ba8e0d965be946c305bdcf562744d827bbb21a0c0ee5
Time Elapsed=5 seconds

k=6, n=25,000,000
xS=00000004f83a186a2955dc4eefd17c43745069410ac2faebc68247b3f9fa56ee
Time Elapsed=25 seconds
* NOTE: Needed to increase n in order to get correct hash (returned “did not find” otherwise) *

Question 2:
k=7, n=100,000,000
xS=0000000aad84d11a6eed26ecac81db007de2c1d884c8ddc2e24aee48dce11363
Time Elapsed=246 seconds

Description:
1 Master and 2 Worker Nodes
Master: 
Machine Type - n1-standard-2 
Disk Type - pd-balanced
Disk Size - 100 gb
Worker: 
Machine Type - n2-standard-4
Disk Type - pd-balanced
Disk Size - 200gb
Process for Finding Optimal n:
Guess and check method. We would begin with a larger than necessary value (to avoid ‘did not find’) and would iteratively decrease the value until we found the smallest working n. 

After using both versions, we found that when k=2 and n=100, the sequential approach failed to find a hash value, outputting ‘did not find’. This pattern also occurred with the following k values, making us believe that the randomized approach is more concise. This makes sense considering how these types of algorithms work, particularly how it ensures unbiased sampling. Here, each potential nonce has an equal opportunity of being tried, which aids in mitigating associated risks with the predictable sequences by reducing the likelihood of different nodes working on numbers already attempted. In other words, when n is sufficiently large, it doesn’t require all n values to be tested, which decreases the total runtime.