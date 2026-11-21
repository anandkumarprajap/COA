```txt
Chapter 1 – Introduction to Computer Organization and Architecture

Chapter 2 – Stored Program Concept and Von Neumann Architecture

Chapter 3 – Register and Bus Organization

Chapter 4 – Instruction Format and Instruction Execution

Chapter 5 – Complete Example: ADD Two Numbers

Chapter 6 – Quick Revision

```

# Computer Organization and Architecture (COA)
## Chapter 1 – Introduction to Computer Organization and Architecture

### 1. What is Computer Organization and Architecture?

**Computer Architecture**

Computer Architecture describes the design and functional behavior of a computer system. It explains what a computer does and how programmers interact with it.

Examples:
- Instruction Set Architecture (ISA)
- Memory addressing
- Data types
- Registers
- Input/Output instructions

**Computer Organization**

Computer Organization describes how different hardware components are connected and work together to execute instructions.

Examples:
- Control Unit (CU)
- Arithmetic Logic Unit (ALU)
- Registers
- Memory
- Data bus
- Control bus

**Difference between Computer Architecture and Organization**

| Computer Architecture | Computer Organization |
|---|---|
| What the computer does | How the computer works |
| Programmer's view | Hardware implementation |
| Instruction set | Control signals |
| Addressing modes | Bus connections |
| Data types | Register design |

### 2. Why Do We Study Computer Organization and Architecture?

We study COA to understand:

1. How a computer executes instructions.
2. How the CPU processes data.
3. How memory stores programs and data.
4. How registers transfer data.
5. How the ALU performs arithmetic and logical operations.
6. How the Control Unit controls hardware.
7. How computer performance can be improved.

### 3. Topics Covered in COA

- Computer Architecture and Organization
- Stored Program Concept
- Von Neumann Architecture
- CPU and its components
- Registers and Register Organization
- Bus Organization
- Memory Organization
- Instruction Format
- Instruction Cycle
- Arithmetic and Logic Operations
- Input/Output Organization
- Computer Performance

### 4. Scope of Computer Organization

The scope includes:

**1. Processor Organization**
- ALU
- Control Unit
- Registers
- Instruction execution

**2. Memory Organization**
- Main Memory
- Cache Memory
- RAM and ROM
- Memory addressing

**3. Input/Output Organization**
- Keyboard
- Mouse
- Monitor
- Input and Output interfaces

**4. Bus Organization**
- Data Bus
- Address Bus
- Control Bus

**5. Performance**
- Clock speed
- Execution time
- CPI (Cycles Per Instruction)
- Throughput

### 5. Computer Performance

Computer performance measures how quickly a computer completes a task.

Important terms:

- **Execution Time:** Time required to execute a program.
- **Clock Speed:** Number of clock cycles per second.
- **CPI:** Average clock cycles required per instruction.
- **Throughput:** Number of tasks completed in a given time.

CPU Execution Time:

CPU Time = Instruction Count × CPI × Clock Cycle Time

A computer with lower execution time generally provides better performance for the same task.

---

# Chapter 2 – Stored Program Concept and Von Neumann Architecture

### 1. What is the Stored Program Concept?

The Stored Program Concept means that both program instructions and data are stored in the computer's main memory.

The CPU fetches instructions from memory, decodes them, and executes them one by one.

**Example:**

```c
int a = 10;
int b = 20;
int c = a + b;
```

Here:
- 10 and 20 are data.
- Addition is an operation.
- The program instructions and data are stored in memory.
- CPU executes the instructions.

### 2. Von Neumann Architecture

Von Neumann Architecture is a computer design in which instructions and data share the same main memory and communication path.

### Block Diagram

```text
              +---------------------+
              |     INPUT UNIT      |
              |   Keyboard, Mouse   |
              +----------+----------+
                         |
                         v
              +---------------------+
              |     MAIN MEMORY     |
              |                     |
              |  Program + Data     |
              |                     |
              +----------+----------+
                         |
                  System Bus
                         |
                         v
              +---------------------+
              |         CPU         |
              |                     |
              |  +---------------+  |
              |  | Control Unit  |  |
              |  +---------------+  |
              |                     |
              |  +---------------+  |
              |  |     ALU       |  |
              |  +---------------+  |
              |                     |
              |  +---------------+  |
              |  |   Registers   |  |
              |  +---------------+  |
              +----------+----------+
                         |
                         v
              +---------------------+
              |     OUTPUT UNIT    |
              |   Monitor, Printer |
              +---------------------+
```

### 3. Components of Von Neumann Architecture

**1. Main Memory**

Main Memory stores:
- Program instructions
- Input data
- Intermediate results
- Final results

**2. CPU (Central Processing Unit)**

CPU is called the brain of the computer.

It contains:
- Control Unit
- Arithmetic Logic Unit
- Registers

**3. Control Unit (CU)**

The Control Unit controls and coordinates all computer operations.

Functions:
- Fetch instructions from memory.
- Decode instructions.
- Generate control signals.
- Control read and write operations.
- Coordinate data movement.

**4. Arithmetic Logic Unit (ALU)**

ALU performs arithmetic and logical operations.

Arithmetic operations:
- Addition (+)
- Subtraction (-)
- Multiplication (×)
- Division (÷)
- Increment
- Decrement

Logical operations:
- AND
- OR
- NOT
- XOR
- Comparison

Shift operations:
- Logical Shift Left (SHL)
- Logical Shift Right (SHR)

**5. Registers**

Registers are small, high-speed storage locations inside the CPU.

They temporarily store:
- Data
- Instructions
- Memory addresses
- Intermediate results

### 4. 8-bit and 16-bit Registers

**8-bit Register**

An 8-bit register contains 8 binary storage positions.

```text
Bit:  7 6 5 4 3 2 1 0
     +---------------+
     | 0 1 0 1 1 0 1 0|
     +---------------+
          8 Bits
```

Example: 8-bit register can represent unsigned values from 0 to 255.

**16-bit Register**

A 16-bit register contains 16 binary storage positions.

```text
Bit: 15 14 13 12 11 10 9 8 7 6 5 4 3 2 1 0
     +-----------------------------------+
     |       16 Binary Bits              |
     +-----------------------------------+
```

Example: 16-bit register can represent unsigned values from 0 to 65,535.

### 5. Stored Program Execution Cycle

The CPU executes instructions using the Fetch–Decode–Execute cycle.

```text
       +------------------+
       |  FETCH           |
       | Get instruction  |
       | from memory      |
       +--------+---------+
                |
                v
       +------------------+
       |  DECODE          |
       | Understand the   |
       | instruction      |
       +--------+---------+
                |
                v
       +------------------+
       |  EXECUTE         |
       | Perform the      |
       | required task    |
       +--------+---------+
                |
                v
       +------------------+
       |  STORE RESULT    |
       | Save the result  |
       +--------+---------+
                |
                v
           Next Instruction
```

The cycle repeats until the program finishes or a control-transfer instruction changes the execution sequence.

### 6. Timing Signals and Control Signals

The Control Unit generates timing and control signals to coordinate CPU operations.

In the basic computer model, timing signals are represented as:

- T0
- T1
- T2
- T3
- T4
- T5 ...

These signals determine when an operation takes place.

Example of instruction fetching:

| Timing | Operation |
|---|---|
| T0 | AR ← PC |
| T1 | IR ← M[AR], PC ← PC + 1 |
| T2 | Decode IR, AR ← IR(0–11), I ← IR(15) |

Here:
- AR = Address Register
- PC = Program Counter
- IR = Instruction Register
- M[AR] = Memory content at address AR

**Important:** T0, T1, T2 are timing signals, not instruction numbers. I is the indirect-addressing bit in the instruction format.

### 7. Memory Read and Write Operations

**Memory Read Operation**

Read means transferring data from memory into a CPU register.

```text
       MAIN MEMORY
       Address 100
           |
           | READ
           v
       +--------+
       |   DR   |
       +--------+
       Data Register
```

Example:

```text
AR ← 100
DR ← M[AR]
```

Meaning: Read the data stored at memory address 100 into DR.

**Memory Write Operation**

Write means transferring data from a CPU register into memory.

```text
       +--------+
       |   DR   |
       +--------+
           |
           | WRITE
           v
       MAIN MEMORY
       Address 100
```

Example:

```text
AR ← 100
M[AR] ← DR
```

Meaning: Write the contents of DR into memory address 100.

### 8. ALU Arithmetic and Logical Operations

Assume:

```text
A = 10 = 00001010
B = 20 = 00010100
```

| Operation | Result (Decimal) |
|---|---:|
| A + B | 30 |
| B - A | 10 |
| A AND B | 0 |
| A OR B | 30 |
| A XOR B | 30 |
| NOT A (8-bit) | 245 |
| A << 1 | 20 |
| B >> 1 | 10 |

Binary examples:

```text
A = 00001010
B = 00010100

Addition:

  00001010
+ 00010100
-----------
  00011110  = 30
```

Logical AND:

```text
  00001010
& 00010100
-----------
  00000000  = 0
```

Shift Left:

```text
A = 00001010

SHL A

    00001010
  → 00010100

Result = 20
```

Note: The above shift is an 8-bit logical shift. The leftmost bit is discarded and zero enters from the right.

### 9. Example: Execute a C Program Using CPU

Program:

```c
int a = 10;
int b = 20;
int c = a + b;
```

Assume:
- Memory address 100 contains 10.
- Memory address 101 contains 20.
- Memory address 102 stores the result.
- The accumulator is used for arithmetic.

Step-by-step execution:

**Step 1: Load a**

```text
AC ← M[100]
AC = 10
```

**Step 2: Add b**

```text
AC ← AC + M[101]

AC = 10 + 20
AC = 30
```

**Step 3: Store c**

```text
M[102] ← AC
```

Memory after execution:

| Address | Value |
|---|---:|
| 100 | 10 |
| 101 | 20 |
| 102 | 30 |

CPU execution visualization:

```text
Memory             CPU
+---------+       +-----------+
| 100 = 10| ----> |           |
+---------+       |     AC    |
                  |     10    |
+---------+       |     +     |
|101 = 20 | ----> |     20    |
+---------+       |-----------|
                  |     30    |
+---------+       +-----+-----+
|102 = 30 | <-----------+
+---------+
```

Final result:

```text
c = 30
```

---

# Chapter 3 – Register and Bus Organization

### 1. What is Register Organization?

Register Organization describes how CPU registers are arranged and connected to transfer and process data.

Registers are used for temporary storage during instruction execution.

### 2. General Purpose Registers (GPR)

General Purpose Registers are CPU registers used to store temporary data, operands, and intermediate results.

Examples:

```text
+------------------+
|       CPU        |
|                  |
|  +------------+  |
|  | Register R0|  |
|  +------------+  |
|  | Register R1|  |
|  +------------+  |
|  | Register R2|  |
|  +------------+  |
|  | Register R3|  |
|  +------------+  |
+------------------+
```

Uses:
- Store operands.
- Hold intermediate results.
- Reduce memory access.
- Speed up processing.

### 3. What is Bus Organization?

A Bus is a communication pathway used to transfer data, addresses, and control signals between computer components.

There are three main types of buses.

**1. Data Bus**

Transfers actual data between CPU, memory, and I/O devices.

**2. Address Bus**

Transfers memory addresses to identify a particular memory location.

**3. Control Bus**

Transfers control signals such as:
- Memory Read
- Memory Write
- Interrupt
- Clock

Bus diagram:

```text
       +--------+
       |  CPU   |
       +---+----+
           |
    +------+------+
    |  SYSTEM BUS |
    +------+------+
           |
     +-----+-----+
     |           |
+----+----+  +---+------+
| MEMORY  |  | I/O UNIT |
+---------+  +----------+
```

### 4. Memory Organization: 4096 × 16

Given:

```text
Memory = 4096 × 16
```

This means:
- Number of words = 4096
- Each word = 16 bits

Total memory capacity:

4096 × 16 = 65,536 bits

4096 = 2^12

Therefore, 12 address bits are required.

**Memory Structure**

```text
          MEMORY
      4096 Words × 16 Bits

Address
 0000  +----------------+
       | 16-bit Word    |
 0001  +----------------+
       | 16-bit Word    |
 0002  +----------------+
       | 16-bit Word    |
       |       ...      |
       |       ...      |
 4094  +----------------+
       | 16-bit Word    |
 4095  +----------------+

       Total 4096 Words
```

Address range:

```text
0 to 4095
```

Binary address range:

```text
000000000000
to
111111111111
```

### 5. Important CPU Registers and Their Sizes

For the 4096 × 16 basic computer model:

| Register | Size | Purpose |
|---|---:|---|
| AR – Address Register | 12 bits | Stores memory address |
| PC – Program Counter | 12 bits | Stores next instruction address |
| DR – Data Register | 16 bits | Stores memory data |
| AC – Accumulator | 16 bits | Stores ALU operands/results |
| IR – Instruction Register | 16 bits | Stores current instruction |
| TR – Temporary Register | 16 bits | Stores temporary data |
| INPR – Input Register | 8 bits | Stores input character/data |
| OUTR – Output Register | 8 bits | Stores output character/data |

**A. Address Register (AR) – 12 Bits**

AR stores the address of the memory location to be accessed.

```text
+--------------------------+
| AR                       |
| 0 1 2 3 4 5 6 7 8 9 10 11|
+--------------------------+
          12 Bits
```

Example:

```text
AR = 000000000100
```

This represents memory address 4.

**B. Program Counter (PC) – 12 Bits**

PC stores the address of the next instruction to be fetched.

Example:

```text
PC = 000000000000

After fetching:
PC = 000000000001

After next fetch:
PC = 000000000010
```

PC normally increments by one after fetching an instruction, unless a branch or jump changes it.

**C. Data Register (DR) – 16 Bits**

DR stores data read from memory.

```text
+-----------------------------------+
| DR                                |
| 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15|
+-----------------------------------+
                16 Bits
```

**D. Accumulator (AC) – 16 Bits**

AC stores arithmetic and logical results.

Example:

```text
AC = 10
DR = 20

AC ← AC + DR

AC = 30
```

**E. Instruction Register (IR) – 16 Bits**

IR stores the instruction currently being decoded or executed.

**F. Temporary Register (TR) – 16 Bits**

TR temporarily stores intermediate information during CPU operations.

**G. Input Register (INPR) – 8 Bits**

INPR receives 8-bit data from an input device.

Example:

```text
Keyboard → INPR
```

**H. Output Register (OUTR) – 8 Bits**

OUTR holds 8-bit data before it is sent to an output device.

Example:

```text
OUTR → Monitor
```

---

# Chapter 4 – Instruction Format and Instruction Execution

### 1. What is an Instruction?

An instruction is a binary command that tells the CPU what operation to perform.

Examples:
- ADD
- SUB
- LOAD
- STORE
- AND
- OR
- JUMP

### 2. Instruction Format (16 Bits)

In the basic computer model, the memory-reference instruction has 16 bits.

```text
 15             14 13 12             0
+---+--------------+-----------------+
| I |    OPCODE    |     ADDRESS     |
+---+--------------+-----------------+
 1       3 Bits         12 Bits

       Total = 16 Bits
```

Explanation:

- I = Indirect addressing bit (1 bit).
- Opcode = Operation code (3 bits).
- Address = Memory address (12 bits).

Total:

1 + 3 + 12 = 16 bits

### 3. Opcode Table

| Opcode | Instruction | Operation |
|---|---|---|
| 000 | AND | AC ← AC AND M[AR] |
| 001 | ADD | AC ← AC + M[AR] |
| 010 | LDA | AC ← M[AR] |
| 011 | STA | M[AR] ← AC |
| 100 | BUN | PC ← AR |
| 101 | BSA | Branch and save return address |
| 110 | ISZ | Increment and skip if zero |
| 111 | Register/I/O | Depends on I bit |

For opcode 111:
- I = 0: Register-reference instruction.
- I = 1: Input/output instruction.

### 4. Direct and Indirect Addressing

**Direct Addressing (I = 0)**

The address field directly specifies the memory location.

```text
Instruction Address = 100

AR ← 100
DR ← M[100]
```

**Indirect Addressing (I = 1)**

The address field specifies a memory location containing the effective address.

Example:

```text
M[100] = 500
M[500] = 20

Instruction Address = 100

AR ← 100
AR ← M[AR]
DR ← M[AR]

DR = 20
```

### 5. Example: Instruction Encoding

Suppose:

```text
LDA 100
```

Opcode for LDA = 010

Direct addressing = I 0

Address 100 in decimal = 000001100100 in 12-bit binary.

Instruction:

```text
I       OPCODE       ADDRESS

0       010          000001100100

0001 0000 0110 0100
```

Complete instruction:

```text
0001000001100100
```

This instruction loads the contents of memory address 100 into AC.

### 6. Instruction Fetch, Decode and Execute

**Fetch Cycle**

```text
T0: AR ← PC

T1: IR ← M[AR]
    PC ← PC + 1
```

**Decode Cycle**

```text
T2: Decode IR(12–14)
    AR ← IR(0–11)
    I ← IR(15)
```

**Execute Cycle**

For ADD:

```text
T4: DR ← M[AR]

T5: AC ← AC + DR
    E ← Carry
```

The exact timing can vary by instruction. For example, indirect addressing adds an effective-address calculation before the operand is accessed.

---

# Chapter 5 – Complete Example: ADD Two Numbers

### Given Program

```c
int a = 10;
int b = 20;
int c = a + b;
```

Assume:

```text
M[100] = 10
M[101] = 20
M[102] = Result
```

The following is a conceptual assembly-style program for the basic computer:

```assembly
LDA 100
ADD 101
STA 102
HLT
```

### Execution Step 1 – LDA 100

```text
PC → Memory → IR

AC ← M[100]

AC = 10
```

### Execution Step 2 – ADD 101

```text
DR ← M[101]

DR = 20

AC ← AC + DR

AC = 10 + 20

AC = 30
```

### Execution Step 3 – STA 102

```text
M[102] ← AC

M[102] = 30
```

### Execution Step 4 – HLT

CPU stops executing the program.

### Final Memory

| Memory Address | Data |
|---|---:|
| 100 | 10 |
| 101 | 20 |
| 102 | 30 |

### Complete CPU Data Flow

```text
             MAIN MEMORY
        +-------------------+
        | 100 = 10          |
        | 101 = 20          |
        | 102 = 00          |
        +---------+---------+
                  |
                  | Data
                  v
        +-------------------+
        |        DR         |
        |      16 Bits      |
        +---------+---------+
                  |
                  v
        +-------------------+
        |        ALU        |
        |     ADDITION      |
        +---------+---------+
                  |
                  v
        +-------------------+
        |        AC         |
        |      16 Bits      |
        |        30         |
        +---------+---------+
                  |
                  | STORE
                  v
             MAIN MEMORY
             M[102] = 30
```

**Final Answer:**

```text
a = 10
b = 20
c = 30
```

---

# Chapter 6 – Quick Revision

| Concept | Important Point |
|---|---|
| Computer Architecture | What the computer does |
| Computer Organization | How hardware works |
| Von Neumann | Same memory for data and instructions |
| Stored Program | Instructions and data stored in memory |
| CPU | CU + ALU + Registers |
| CU | Controls CPU operations |
| ALU | Arithmetic and logical operations |
| Register | High-speed temporary storage |
| Bus | Communication pathway |
| AR | 12 bits |
| PC | 12 bits |
| DR | 16 bits |
| AC | 16 bits |
| IR | 16 bits |
| TR | 16 bits |
| INPR | 8 bits |
| OUTR | 8 bits |
| Memory | 4096 × 16 |
| Address Bits | 12 bits |
| Word Size | 16 bits |
| Instruction Size | 16 bits |
| Opcode | 3 bits |
| I Bit | 1 bit |
| Address Field | 12 bits |

## Important Formulas

1. Number of address bits = log₂(Number of memory words)

2. Memory Capacity = Number of Words × Word Size

3. CPU Execution Time = Instruction Count × CPI × Clock Cycle Time

4. Instruction Size = I Bit + Opcode + Address

## Practice Questions

1. What is Computer Organization and Architecture?
2. Explain the difference between Architecture and Organization.
3. What is the Stored Program Concept?
4. Draw and explain Von Neumann Architecture.
5. Explain the functions of CU and ALU.
6. What is the difference between an 8-bit and 16-bit register?
7. Explain the Fetch–Decode–Execute cycle.
8. Explain Memory Read and Write operations.
9. What is Register Organization?
10. Explain General Purpose Registers.
11. What is Bus Organization? Explain three types of buses.
12. Calculate the address bits required for 4096 memory words.
13. Explain the functions of AR, PC, DR, AC, IR and TR.
14. Explain the 16-bit instruction format.
15. Explain direct and indirect addressing.
16. Execute an ADD instruction using the CPU registers.
