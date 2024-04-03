---
layout: post
author: Cascal Pascal
tags:
  - major
  - computer-architecture
  - tech-interview
---

>**Course**
>
>[[Major] Computer Architecture](https://cascalpascal.github.io/major-tech-interview)

>**Bookmarks**
>
>- [Operation Principle of CPU](#operation-principle-of-central-processing-unit(cpu))
>
>- [CPU operation process](#cpu-operation-process)


---

<br>

# Operation Principle of Central Processing Unit(CPU)  
The CPU plays the most critical role in a computer sustem, often referred to as the "brain". It consists of three main components: the Arithmetic Logic Unit, the Control Unit, and registers.

<br>

## - Arithmetic Logic Unit(ALU)
Performs arithmetic and logical operations. It retrieves data required for operations from registers and sends the operation results back to registers.

<br>

## - Control Unit
Coordinates the execution of instructions in sequence. It retrieves program instructions from the main memory, interprets them, and based on the results, sends control signals required for instruction execution to the main memory, ALU, and input/output devices. Additionally, it receives signals sent by these devices to determine the next operation to be performed.

<br>

## - Registers
High-speed memory units that temporarily store various types of data, including instruction addresses, codes, data required for operations, and operation results. The number and size of registers available vary depending on the type of CPU.

Registers are classified into two types:

- General-purpose registers: Temporarily store data required for operations or operation results.
- Special-purpose registers: Used for specific purposes.

Some of the important special-purpose registers include:

1. **Memory Address Register (MAR)**: Stores the address of the main memory location to perform read and write operations.
    
2. **Program Counter (PC)**: Stores the address of the next instruction to be fetched and executed.
    
3. **Instruction Register (IR)**: Stores the currently executing instruction.
    
4. **Memory Buffer Register (MBR)**: Temporarily stores data read from or to be written to the main memory.
    
5. **Accumulator (AC)**: Temporarily stores the results of arithmetic and logical operations.

<br>

---

#  CPU operation process
1. The main memory fetches data or programs stored in secondary memory or received from input devices.
2. The CPU retrieves program instructions and data stored in main memory to execute the program. It processes the data and instructions and stores the results back in main memory.
3. The main memory stores the processed results in secondary memory or sends them to output devices.
4. The control unit ensures that the instructions are executed sequentially in steps 1 to 3.

<br>

## Instruction Set
An instruction set is a collection of instructions that the CPU can execute. It consists of an operation code (opcode) and operands.

> opcode: 실행할 연산
> operands: 필요한 데이터 or 저장 위치

- Opcode: Specifies the operation to be performed. Include operations related to arithmetic, control, data transfer, and input/output functions.
- Operands: Provide data or storage locations needed for the operation. Store addresses, numbers/characters, logical data, etc.

The CPU repeatedly performs the following steps to execute a program stored in main memory:

- *Fetches* one instruction at a time from main memory.
- Decodes and *executes* the instruction during the execution cycle.
- Once the execution of one instruction is complete, the next instruction fetch cycle begins from the specified address in main memory.

This sequence of activities required for fetching and executing one instruction is called an "*instruction cycle*," which is divided into fetch/execution/indirect/interrupt cycles.

<br>

## The process of fetch and execution cycle

> In the fetch cycle, the most critical aspect is the increment of the Program Counter(PC) value.

### Fetch Cycle
- ```T0```: The address stored in the PC is transmitted to the Memory Address Register (MAR). Based on the stored address, the instruction is fetched from the corresponding memory location in the main memory.
- ```T1```: The fetched instruction is stored in the Memory Buffer Register (MBR). The PC value is incremented to fetch the next instruction.
- ```T2```: The content stored in the Memory Buffer Register (MBR) is transferred to the Instruction Register (IR).

```
T0 : MAR ← PC
T1 : MBR ← M[MAR], PC ← PC + 1
T2: IR ← MBR
```

### Execution Cycle

```
T0 : MAR ← IR(Addr)
T1 : MBR ← M[MAR]
T2 : AC ← AC + MBR
```



<br>

---

## Reference
https://gyoogle.dev/blog/computer-science/computer-architecture/%EC%A4%91%EC%95%99%EC%B2%98%EB%A6%AC%EC%9E%A5%EC%B9%98%20%EC%9E%91%EB%8F%99%20%EC%9B%90%EB%A6%AC.html