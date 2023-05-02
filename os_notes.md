# Review list

Conception bullet points:
 - [x] Memory manager
    - Address Mapping
    - Logical Addresses
    - Physical Addresses
    - Memory Allocation
      - Contiguous
        - Fixed
        - Variable
      - Non-Contiguous
        - Paging
        - Segmentation
        - Paged Segmentation
 
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

## Memory Management Concepts

### Address Mapping

Address mapping is the process of translating logical addresses into physical addresses. Logical addresses are the addresses that a program uses, which are typically contiguous and start at zero. Physical addresses are the addresses that correspond to locations in memory, which may be different from the logical addresses due to address mapping.

### Logical Addresses

Logical addresses are the addresses that a program uses, which are typically contiguous and start at zero. They are virtual addresses that are used by the program and do not necessarily correspond to physical addresses.

### Physical Addresses

Physical addresses are the addresses that correspond to locations in memory. They may be different from the logical addresses due to address mapping. Physical addresses are used by the hardware to access memory.

### Memory Allocation

Memory allocation is the process of assigning memory to different programs or processes.

#### Contiguous

Contiguous memory allocation is a technique where a program's memory is allocated in one contiguous block. There are two types of contiguous memory allocation:

##### Fixed

Fixed contiguous memory allocation is a type where a program is allocated a fixed block of memory that cannot be resized.

##### Variable

Variable contiguous memory allocation is a type where a program is allocated a block of memory that can be resized as needed.

#### Non-Contiguous

Non-contiguous memory allocation is a technique where a program's memory is scattered across different non-contiguous blocks of memory.

##### Paging

Paging is a non-contiguous memory allocation technique where memory is divided into fixed-size pages, and a program's pages can be allocated anywhere in memory.

##### Segmentation

Segmentation is a non-contiguous memory allocation technique where memory is divided into logical segments. Each segment is allocated separately to a program.

##### Paged Segmentation

Paged segmentation is a combination of paging and segmentation, where memory is divided into segments, and each segment is further divided into pages.```

--------
  



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
