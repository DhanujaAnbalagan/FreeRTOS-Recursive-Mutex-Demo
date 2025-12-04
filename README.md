# FreeRTOS Recursive Mutex Example (ESP32)

This project demonstrates the use of a **recursive mutex** in FreeRTOS using an ESP32.  
Two tasks attempt to control two LEDs, and a recursive mutex ensures synchronized access without causing deadlocks.

---

## 📌 What is a Recursive Mutex?

A **recursive mutex** allows the **same task** to acquire the mutex multiple times without blocking itself.

Unlike a normal mutex:

| Feature | Normal Mutex | Recursive Mutex |
|---------|--------------|----------------|
| Can same task lock multiple times? | ❌ Deadlock | ✔ Allowed |
| Lock counter stored? | No | Yes |
| Used in nested function calls? | No | Yes |

---

## 🧠 Use Case

Recursive mutexes are useful when:

- A function acquires a mutex
- Then calls another function that also needs the same mutex

This avoids self-deadlock.

---

## 🧰 Hardware Requirements

| Component | Quantity |
|----------|----------|
| ESP32 | 1 |
| 2 LEDs | 2 |
| Resistors (220Ω) | 2 |
| Jumper wires | Required |

---

## ⚙ Code Overview

- Two FreeRTOS tasks (`task1` and `task2`)
- Both try to access a **shared critical section**
- Mutex ensures only one runs the LED sequence at a time



```cpp
// (Your full code goes here)
