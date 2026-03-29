Here’s a well-structured **GitHub README** for your **Fibonacci Sequence Implementation in Proteus**:  

---

# **Fibonacci Sequence Implementation using Proteus**  

![Proteus Simulation](./fibonacci_image.jpg) 
## 📌 **Project Overview**  
This project demonstrates the **Fibonacci sequence generation** using a **microcontroller-based embedded system** in **Proteus**. The simulation illustrates how the Fibonacci series is computed and displayed on an **LCD screen**, making it suitable for **educational and embedded systems applications**.  

## 🚀 **Technologies & Tools Used**  
- **Proteus** – Circuit simulation & microcontroller-based system design  
- **Microcontroller (e.g., ATmega16, PIC16F877A, or 8051)** – Implements the Fibonacci logic  
- **C/Assembly Language** – Code for Fibonacci sequence computation  
- **LCD Display (16x2)** – Real-time visualization of Fibonacci numbers  
- **Keil uVision/MPLAB/XC8** – Code compilation and debugging  

## 🔧 **Project Features**  
✅ **Fibonacci Series Calculation** – Computes Fibonacci numbers iteratively or recursively.  
✅ **LCD Display Integration** – Displays computed Fibonacci numbers in real-time.  
✅ **Efficient Memory Usage** – Optimized for minimal stack usage and better performance.  
✅ **Embedded System Simulation** – Simulated in **Proteus** for real-world microcontroller applications.  

## 📜 **Project Structure**  
```
📂 Fibonacci-Proteus/
 ├── 📁 Fibonacci.pdsrj     # Contains the .pdsprj file and circuit design
 ├── 📝 README.md            # Documentation (this file)
 ├── 📷 Screenshots/         # Images of the simulation output
```

## 🛠 **Installation & Simulation Guide**  
1. **Clone the repository**  
   ```bash
   git clone https://github.com/Aayush-Patidar/Fibonacci-Proteus.git
   cd Fibonacci-Proteus
   ```
2. **Open the Proteus file**  
   - Navigate to the **Proteus_Project** folder and open `Fibonacci.pdsprj` in **Proteus 8.0 or later**.  
3. **Load the microcontroller code**  
   - Compile the **C/Assembly code** in **Keil uVision** or **MPLAB XC8**.  
   - Upload the `.hex` file to the **microcontroller in Proteus**.  
4. **Run the simulation**  
   - Click the **Run** button in Proteus and observe the Fibonacci series on the **LCD screen**.  

## 📸 **Project Demo**  
*(Add simulation screenshots here)*  

## 🔗 **GitHub Repository**  
[👉 Fibonacci Sequence in Proteus](https://github.com/Aneket-Burman/Fibonacci-Proteus) *(Replace with actual link once uploaded)*  

---

This **README** is **structured, informative, and optimized** for **GitHub**, making it easy for others to understand and use your project. Let me know if you need any changes! 🚀   
// code ORG 0000H

MOV R0, #30H      ; pointer to memory location
MOV A, #00H       ; first number = 0
MOV @R0, A        ; store 0

INC R0            ; move to next location
MOV A, #01H       ; second number = 1
MOV @R0, A        ; store 1

MOV R2, #08       ; number of terms (change as needed)

LOOP:
    MOV A, @R0        ; get last number
    MOV R3, A         ; store in R3

    DEC R0            ; go to previous number
    MOV A, @R0        ; get previous number

    ADD A, R3         ; A = prev + last

    INC R0            ; go back to current position
    INC R0            ; move to next position

    MOV @R0, A        ; store new Fibonacci number

    DJNZ R2, LOOP     ; repeat

HERE: SJMP HERE       ; stop program

END

