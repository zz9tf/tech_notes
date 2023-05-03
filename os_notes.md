# Review list

Conception bullet points:
 - [x] Memory Management: Address Mapping, Logical Addresses, Physical Addresses, Memory Allocation, Contiguous (Fixed, Variable), Non-Contiguous (Paging, Segmentation, Paged Segmentation)
 
- [x] Visual memory
   - Swapping vs. Demand Paging
      - Swapping
      - Demand Paging
   - Virtual Memory
   - Address Translation
   - Page Faults
   - Page Replacement
   - Effective Access Time
   - Page Replacement Policies
     - FIFO

-------

## Memory Management

1. **Address Mapping**: Address mapping is the process of translating logical addresses into physical addresses used in MAR. Generated at runtime (execution time) by memory management unit (MMU) of CPU. This protocol enables dynamic program relocation without having to modify program code.

<img width="489" alt="image" src="https://user-images.githubusercontent.com/77183284/235819131-58b408e6-8872-4cac-aabd-d1eca2d70f95.png">

2. **Logical Addresses**: Logical addresses are an Abstraction of Memory, which must be mapped to physical addresses. "Placeholder" addresses which need to be adjusted before they can be used. 

     PS: Logical address: contains two parts.
      
      - p:	page number: index into page table which contains base address of corresponding frame
      - d:	page offset:  added to base address to find location within page/frame
      - s:	segment number：index into segment table which contains limit and base address of corresponding segment
      - d:	segment offset

<img width="586" alt="image" src="https://user-images.githubusercontent.com/77183284/235817911-591b5d4f-6e6f-43d6-9883-25a6eaec734d.png">

3. **Physical Addresses**: Physical addresses are the addresses that correspond to locations in MRA.

4. **Memory Allocation**: Memory allocation is responsible for allocating memory to processes
   
   a. **Contiguous**: Contiguous allocation of process P (no gaps)
   
   +: Easy implementation, Easy to conceptualize
   
   -: Poor memory utilization

      - **Fixed**: This policy divide memory a priori into fixed partitions
        - **Allocation Policy**: choose partition (Ri) that is smallest but >= k (best-fit)
        - **Utilization Issue**: internal fragmentation:  parts of allocated partition unused
        <img width="670" alt="image" src="https://user-images.githubusercontent.com/77183284/235820224-9d718599-e4c7-4b83-87a7-0b31a034d824.png">
      - **Variable**: Allocate memory chunks as needed. Different size chunks will be signed different size spaces
        policy | explaination | + | -
        -|-|-|-
        Best-fit | choose hole that is smallest but ≥ k (B) +reserves big holes for big processes | reserves big holes for big processes | creates many external fragmentation
        Worst-fit | choose largest hole (D) | creates relative even-sized holes, since they all become smaller | many of the holes unusable, with large holes become smaller
        First-fit | choose first hole with size ≥ k (A) | |
        Next-fit |  choose next hole with size ≥ k | easy to implement | best/worst fit hard to assess


   b. **Non-Contiguous**: Non-Contiguous allocation of process P (with gaps)

      - **Paging**: Paging is a non-contiguous memory allocation technique where memory is divided into fixed-size pages, and a program's pages can be allocated anywhere in memory.

      - **Segmentation**: Partitions of logical address space / physical memory are variable, not fixed. Partitions based on **conceptual divisions** rather then page size

      - **Paged Segmentation**: Paged segmentation is a combination of paging and segmentation, where memory is divided into segments, and each segment is further divided into pages.

<img width="613" alt="image" src="https://user-images.githubusercontent.com/77183284/235818831-20f8b7cf-90f0-416f-8639-66e21a3176a7.png">

--------
  

## Virtual memory

### Swapping vs. Demand Paging
- **Swapping:** An entire process is moved between main memory and secondary storage.
- **Demand Paging:** Only the necessary pages are moved between main memory and secondary storage.
### Virtual Memory
- **Virtual Memory:** An abstraction of the physical memory that allows a process to use more memory than is physically available.
- **Address Translation:** The process of translating virtual addresses to physical addresses.
### Page Faults
- **Page Faults:** Occur when a process attempts to access a page that is not currently in main memory.
- **Page Replacement:** The process of replacing a page in main memory with a page from secondary storage.
- **Effective Access Time:** The average time required to access a page, including both the time to access main memory and the time to perform page replacement.
### Page Replacement Policies
- **FIFO:** Replace the oldest page in main memory.
- **Optimal:** Replace the page that will not be used for the longest period of time in the future.
- **LRU:** Replace the least recently used page in main memory.
- **Approximations of LRU:** Use a less accurate method to approximate LRU, such as the Clock algorithm or the Second Chance algorithm.
- **LFU:** Replace the least frequently used page in main memory.
### Frame Allocation
- **Fixed Allocation:** Each process is given a fixed number of frames in main memory.
- **Priority Allocation:** Allocate frames to processes based on priority.
- **Proportional Allocation:** Allocate frames to processes based on their size.
### Thrashing
- **Thrashing:** Occurs when a process spends more time paging than executing.
- **Working-Set Algorithm:** Attempts to prevent thrashing by dynamically adjusting the number of frames allocated to a process.
- **Adaptive Algorithm (Page-Fault Frequency):** Attempts to prevent thrashing by monitoring the page-fault rate and adjusting the number of frames allocated to a process accordingly.
