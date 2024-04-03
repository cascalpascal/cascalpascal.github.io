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
>- [Configuration of Computer](# configuration-of-computer)
>
>- [Hardware](# hardware)
>
>- [Software](# software)


---

<br>

# Configuration of Computer
- Hardware: Mechanical devices that make up a computer
- Software: A set of instructions that directs and controls the operation of hardware

A computer basically consists of **reading**, **processing**, and then **writing**.

(READ → PROCESS → WRITE)

During this process, it constantly communicates with main memory (RAM). At this time, if the operating system is 64 bit, the CPU reads data from RAM 64 bits at a time.

<br>

## Hardware
- Center Processing Unit
- Memory device: RAM, HDD
- Input/Output device: mouse, printer

![[Pasted image 20240328090429.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240328090429.png?raw=true)

Hardware consists of a CPU, memory, and input/output devices. They are connected by a **system bus**, which carries data and command control signals to each device.

<br>

### Center Processing Unit
In humans, this is the part of the brain. It reads and processes program insructions and data from main memory and controls the execution order of instructions.

It consists of an **arithmatic logic unit(ALU)** that is responsible for comparision and calculation, a **control unit** that is responsible for interpreting  and executing instructions, and a **resgister** that is a fast data storage location.

In small computers such as personal computers, the cpu is also called a **microprocessor**.

<br>

### Memory Device
Storage device for storing intermediate results of programs, data, and operations.

It is divided into main memory and secondary memory, and includes both RAM and ROM. It temporarily stores data needed for programs such as running programs.

Secondary memory refers to devices like hard disks, and although it is slower than main memory, it has the advantage of permanently storing a lot of data.

<br>

### Input/Output device
An input device is a device that inputs data into the computer (keyboard, mouse, etc.).

An output device is a device that expresses externally from a computer (printer, moniter, speaker, etc.).

<br>

### System bus
Wires that physically connect hardware components. They serve as channels through which each component can send data to other components. They are devided into data bus, address bus, and control bus.

- Data bus: A bus that transfers data between the central processing unit and other devices. It is a **bidirectional** bus that sends commands and data from memory and input/output devices to the CPU, or sends the results of operations from the CPU to memory and input/output devices.
- Address bus: In order to accurately transport data, a memory 'address' must be determined. The address bus is a one-way bus because it is a passage through which the central processing unit transfers memory  addresses to main memory or input/output devices.
- Control bus: Since the address bus and the data bus are shared by all devices, there is a need for a means to control them. The control bus serves as a channel through which the central processing unit communicates control signals to memory and input/output devices. The control bus is a **bidirectional** bus because it performs both read  and write operations. Type of control signals include: memory read and write, bus request and grant, interrupt request and acknowledge, clock, reset, etc.

<br>

## Software
- System software: operating system, compiler
- Application software: word processor, spread sheet


<br>



---

## Reference

https://gyoogle.dev/blog/computer-science/computer-architecture/%EC%BB%B4%ED%93%A8%ED%84%B0%EC%9D%98%20%EA%B5%AC%EC%84%B1.html