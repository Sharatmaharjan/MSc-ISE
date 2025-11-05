## 1. Digital Communication and Error Control Coding

### 1(a) Analog vs. Digital Communication Systems
The inevitable shift from analog to **digital communication systems** is driven by several inherent advantages of digital technology, despite the associated costs.

| Feature | Analog Communication System | Digital Communication System |
| :--- | :--- | :--- |
| **Noise & Interference** | Signal quality severely degrades over long distances due to noise accumulation. | Highly **immune to noise** and interference, as noise must be large enough to change a '1' to a '0' or vice-versa. Repeaters can regenerate a clean signal. |
| **Integration** | Difficult to combine signals of different formats (e.g., voice, data, video). | Naturally integrates all signal types (voice, data, video) into a unified binary format for transmission. |
| **Security & Privacy** | Security measures like encryption are generally more complex and less robust. | **Simple and robust encryption/decryption** techniques can be easily implemented using digital coding algorithms. |
| **Flexibility** | Less flexible; system changes often require hardware modification. | Highly flexible; functions like switching, multiplexing, and processing are largely controlled by **software**. |
| **Hardware** | Analog circuits are less complex. | Digital circuits, based on microprocessors and VLSI, are highly complex but also **compact, reliable, and inexpensive** to reproduce. |
| **Cost** | **Inexpensive for short distances** but expensive for long-haul due to repeated amplification of noise. | **High initial cost** for Analog-to-Digital (A/D) and Digital-to-Analog (D/A) conversion hardware, but **economical for long-haul** due to efficient signal regeneration and multiplexing. |

**Inevitable Change and Associated Cost:**
The change is **inevitable** because digital systems offer a fundamental improvement in **signal quality, flexibility, and security**, enabling modern, high-speed data services (like the Internet, mobile networks, and digital TV). The primary **cost** associated with this change is the **high initial investment** in the complex hardware required for A/D and D/A conversion, especially the sampler, quantizer, and coder, which are necessary to digitize the analog message signal.

***

### 1(b) Need for Error Control Coding and Redundancy

The **need for error control coding** is justified by the fact that the communication channel is imperfect (noisy). Noise, interference, and other channel impairments can corrupt the transmitted data, causing a binary '1' to be received as a '0' or a '0' as a '1' (bit error). **Error control coding** intentionally adds structured **redundancy** to the message before transmission, enabling the receiver to detect and often correct these errors, thereby improving the reliability and integrity of the communication link.

**Types of Error Control Coding Techniques:**
1.  **Block Codes:** The message is divided into fixed-size blocks, and parity bits are added to each block independently. Examples include **Linear Block Codes**, **Cyclic Codes** (e.g., CRC), and **Hamming Codes**.
2.  **Convolutional Codes:** Parity bits are calculated based on the current and a few previous message bits, treating the data stream as a whole.

**Illustration with Redundancy (Single-Bit Error Detection):**

* **Technique:** **Single-Parity Check Code** (Block Code)
* **Method:** A single redundant bit (the **parity bit**) is added to a block of $k$ message bits. This bit is chosen so that the total number of '1's in the resulting codeword is either **even** (Even Parity) or **odd** (Odd Parity).
* **Example (Even Parity):**
    * **Original Data:** `1011` (3 ones)
    * **Codeword:** `1011` + **1** (Parity bit to make 4 ones total) $\rightarrow$ **`10111`**
* **Error Detection:**
    * Suppose the codeword `10111` is transmitted, and a single-bit error occurs in the third position: `10011`.
    * The receiver counts the number of '1's in the received word: **3 ones** (an odd number).
    * Since the system is set up for Even Parity, the receiver detects an **error**.
    * *Correction is not possible with just one parity bit; the receiver only knows an error occurred, not its location.*

**Illustration with Redundancy (Error Detection and Correction):**

* **Technique:** **Hamming Code** (Block Code)
* **Method:** Multiple parity bits ($p$) are strategically added to $k$ message bits to form a codeword of length $n=k+p$. The positions and values of these parity bits are chosen to uniquely identify the location of a single-bit error.
* **Result:** With enough redundancy ($2^p \ge n+1$), the code can detect and correct a single-bit error.

***

## 2. AM Modulation and Power Calculation

### 2(a) AM Power Calculation

The total power provided by the transmitter is the total transmitted power $P_{total}$. This power is distributed between the carrier and the sidebands.

**Given:**
* Transmitter Rating = $12 \text{ KW}$
* Power Efficiency ($\eta$) = $90\% = 0.9$
* Modulation Percentage ($m$) = $60\% = 0.6$

**1. Calculate Total Transmitted Power ($P_{total}$):**
$$P_{total} = \text{Transmitter Rating} \times \eta$$
$$P_{total} = 12 \text{ KW} \times 0.9 = 10.8 \text{ KW}$$

**2. Calculate Carrier Power ($P_C$):**
The total transmitted power in a Double Sideband Amplitude Modulation (DSB AM) system is given by the formula:
$$P_{total} = P_C \left(1 + \frac{m^2}{2}\right)$$
Rearranging the formula to solve for $P_C$:
$$P_C = \frac{P_{total}}{1 + \frac{m^2}{2}}$$
$$P_C = \frac{10.8 \text{ KW}}{1 + \frac{(0.6)^2}{2}} = \frac{10.8 \text{ KW}}{1 + \frac{0.36}{2}} = \frac{10.8 \text{ KW}}{1.18}$$
$$P_C \approx 9.153 \text{ KW}$$

**3. Calculate Sideband Power ($P_{SB}$):**
The power in the sidebands is the difference between the total power and the carrier power:
$$P_{SB} = P_{total} - P_C$$
$$P_{SB} = 10.8 \text{ KW} - 9.153 \text{ KW} = 1.647 \text{ KW}$$

**Answer:**
* **Carrier Power ($P_C$) is approximately $\mathbf{9.153 \text{ KW}}$.**
* **Sideband Power ($P_{SB}$) is approximately $\mathbf{1.647 \text{ KW}}$.**

***

### 2(b) Modulation and AM vs. FM Comparison

**1. Define Modulation:**
**Modulation** is the process of superimposing a low-frequency message (or baseband) signal onto a high-frequency sinusoidal **carrier wave**. This process varies a characteristic of the carrier (amplitude, frequency, or phase) in proportion to the instantaneous value of the message signal, making the signal suitable for efficient long-distance transmission over a channel.

**2. Types of Modulation:**
Modulation techniques are primarily categorized based on the carrier characteristic that is varied:

* **Analog Modulation:**
    * **Amplitude Modulation (AM):** The **amplitude** of the carrier is varied.
    * **Frequency Modulation (FM):** The **frequency** of the carrier is varied.
    * **Phase Modulation (PM):** The **phase** of the carrier is varied.
* **Digital Modulation (Keying Techniques):**
    * **Amplitude Shift Keying (ASK):** The amplitude of the carrier is shifted.
    * **Frequency Shift Keying (FSK):** The frequency of the carrier is shifted.
    * **Phase Shift Keying (PSK):** The phase of the carrier is shifted.

**3. Compare AM and FM:**

| Feature | Amplitude Modulation (AM) | Frequency Modulation (FM) |
| :--- | :--- | :--- |
| **Noise Immunity** | Poor. Noise, which is primarily amplitude-based, directly affects the signal amplitude. | Good. Noise affects the amplitude, but the information is in the frequency, which makes it less susceptible to noise interference. |
| **Bandwidth (BW)** | Narrow. $BW = 2 \times f_m$ (where $f_m$ is the message signal's max frequency). | Wide. $BW \approx 2(\Delta f + f_m)$ (where $\Delta f$ is the frequency deviation). |
| **Transmitted Power** | Total power is variable and depends on the modulation index. Power efficiency is poor since most power is in the carrier. | Total power is constant, independent of the modulating signal. |
| **Complexity** | Simple transmitter and receiver circuitry. | More complex transmitter and receiver circuitry (e.g., presence of a limiter). |
| **Broadcast Service** | Used for standard broadcast radio (MW and SW). | Used for high-quality music broadcast (VHF/UHF bands). |

***

## 3. Source Coding (Entropy and Huffman Coding)

### 3(a) Entropy and Huffman Coding

**Given:**
* Alphabet $A = \{-2, -1, 0, 1, 2\}$
* Probabilities $P(A) = \{1/2, 1/4, 1/8, 1/16, 1/16\}$

**i) Find the Source Entropy ($H$):**

Source Entropy is the average uncertainty or the theoretical minimum average number of bits required to represent the source symbols.
$$H = \sum_{i} P_i \log_2 \left(\frac{1}{P_i}\right) \text{ bits/symbol}$$

$$H = \left(\frac{1}{2} \log_2 2\right) + \left(\frac{1}{4} \log_2 4\right) + \left(\frac{1}{8} \log_2 8\right) + \left(\frac{1}{16} \log_2 16\right) + \left(\frac{1}{16} \log_2 16\right)$$

$$H = \left(\frac{1}{2} \times 1\right) + \left(\frac{1}{4} \times 2\right) + \left(\frac{1}{8} \times 3\right) + \left(\frac{1}{16} \times 4\right) + \left(\frac{1}{16} \times 4\right)$$

$$H = 0.5 + 0.5 + 0.375 + 0.25 + 0.25$$
$$H = \mathbf{1.875 \text{ bits/symbol}}$$

**ii) What is the average number of bits necessary to represent this alphabet?**

The average number of bits necessary to represent a Discrete Memoryless Source (DMS) using an optimal coding scheme is the **Source Entropy** ($H$).
$$\text{Average Number of Bits} = H = \mathbf{1.875 \text{ bits/symbol}}$$

**iii) Derive the binary representation of the source symbols by using Huffman coding:**

Huffman coding is an optimal prefix-free code that achieves the minimum average code length (the entropy).

| Symbol | Probability ($P_i$) | Step 1: Merge $1, 2$ ($1/16+1/16 = 1/8$) | Step 2: Merge $0, \{1, 2\}$ ($1/8+1/8 = 1/4$) | Step 3: Merge $-1, \{0, 1, 2\}$ ($1/4+1/4 = 1/2$) | Codeword |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **-2** | **1/2** | $1/2$ | $1/2$ | $1/2 \rightarrow \mathbf{0}$ | **0** |
| **-1** | **1/4** | $1/4$ | $1/4$ | $1/2 \rightarrow \mathbf{10}$ | **10** |
| **0** | **1/8** | $1/8$ | $1/4 \rightarrow \mathbf{110}$ | | **110** |
| **1** | **1/16** | $1/8 \rightarrow \mathbf{1110}$ | | | **1110** |
| **2** | **1/16** | | | | **1111** |
| **$L_{avg}$ Check:** | | $1(1/2) + 2(1/4) + 3(1/8) + 4(1/16) + 4(1/16) = 1.875 \text{ bits/symbol}$ | | | |

| Symbol | Binary Representation (Huffman Code) |
| :---: | :---: |
| **-2** | **0** |
| **-1** | **10** |
| **0** | **110** |
| **1** | **1110** |
| **2** | **1111** |

***

## 4. Communication System and Multiplexing

### 4(a) Communication System and Satellite Communication

**1. Communication System:**
A communication system is a collection of electrical and electronic components and sub-systems that are designed to transfer a message (information) from a **source** to a **destination** over a distance.

**2. Block Diagram of Satellite Communication System:**
A basic satellite communication system consists of a ground segment (Earth Stations) and a space segment (the satellite).

* **Earth Station (Transmitter):** Collects data, modulates the signal, and transmits it to the satellite using a high-gain antenna (Uplink).
* **Uplink:** The communication channel from the transmitting Earth Station to the satellite, operating at a specific uplink frequency (e.g., 5.9-6.4 GHz).
* **Transponder (on the Satellite):** This is a critical component that acts as a repeater. It receives the weak uplink signal, amplifies it, changes its frequency (using a mixer and local oscillator) to a lower downlink frequency, and re-transmits it back to the Earth.
* **Downlink:** The channel from the satellite to the receiving Earth Station, operating at a lower downlink frequency (e.g., 3.7-4.2 GHz).
* **Earth Station (Receiver):** Receives the downlink signal, amplifies it (with a Low-Noise Amplifier), demodulates it, and processes the original information.

**3. Importance for a Country like Nepal:**

Satellite communication is extremely important for a geographically challenging country like Nepal:

* **Connectivity in Remote/Hilly Areas:** Due to its rugged terrain, laying out terrestrial lines (fiber or cable) is difficult and expensive. Satellites provide **uniform coverage** over a wide geographical area, ensuring every corner of the country can be connected, which is crucial for remote villages and disaster management.
* **National and International Linkage:** It provides reliable high-capacity links for **telecommunication, television broadcasting**, and high-speed **Internet access**, which are vital for economic development and education.
* **Disaster Management:** Satellite links are often the only communication means that survive or can be rapidly deployed during natural disasters (like earthquakes or floods) when terrestrial infrastructure fails.

***

### 4(b) Multiplexing and FDM

**1. What is Multiplexing?**
**Multiplexing** is a set of techniques that allows multiple independent signals (or data streams) to be simultaneously transmitted over a single shared physical communication channel (or data link). This efficiently utilizes the high bandwidth capacity of the link, which is generally greater than the bandwidth required by any single signal. The device that combines the signals is a **multiplexer**, and the device that separates them at the receiver is a **demultiplexer**.

**2. Explain about FDM in Brief:**
**Frequency Division Multiplexing (FDM)** is an **analog multiplexing** technique where the total bandwidth of the communication medium is divided into a series of non-overlapping frequency bands, with each band carrying a separate signal.

* **Principle:** Each message signal modulates a unique, high-frequency **carrier wave** ($f_{c1}, f_{c2}, f_{c3},...$).
* **Process:** The different carrier frequencies are spaced far enough apart that their resulting passbands (channels) do not overlap, separated by small unused frequency ranges called **guard bands** to prevent interference (cross-talk).
* **Composite Signal:** All modulated signals are then summed up to form a single, composite signal that is transmitted over the shared medium.
* **Demultiplexing:** At the receiver, **Bandpass Filters** are used to isolate the desired carrier frequency and its sidebands, which is then demodulated to recover the original message signal.
* **Examples:** FDM is widely used in traditional **AM and FM radio broadcasting** and in cable television systems.

***

## 5. Optical Fiber and Digital System Model

### 5(a) Optical Fiber Power Budget Analysis

**Power Budget Analysis** determines if the available optical power from the transmitter is sufficient to overcome all losses in the optical link and still meet the minimum sensitivity required by the receiver.

**Given Data:**
* Link length ($L$): $185 \text{ km}$
* Transmitter power ($P_T$): $1 \text{ mW} = 0 \text{ dBm}$ ($10 \log_{10}(1) = 0 \text{ dBm}$)
* Receiver sensitivity ($P_R$): $-28 \text{ dBm}$
* Fiber attenuation ($\alpha$): $0.25 \text{ dB/km}$
* Number of Splices ($N_S$): $46$
* Splice Loss ($L_S$): $0.1 \text{ dB/splice}$
* Number of Connectors ($N_C$): $2$
* Connector Loss ($L_C$): $0.2 \text{ dB/connector}$

**1. Calculate Power Budget (Available Power) $P_B$:**
The power budget is the maximum permissible loss the link can tolerate.
$$P_B = P_T(\text{dBm}) - P_R(\text{dBm})$$
$$P_B = 0 \text{ dBm} - (-28 \text{ dBm}) = \mathbf{28 \text{ dB}}$$

**2. Calculate Total Channel Loss ($L_{Total}$):**
The total loss is the sum of all losses in the fiber link.
$$L_{Total} = L_{Fiber} + L_{Splice} + L_{Connector}$$

* **Fiber Loss ($L_{Fiber}$):**
    $$L_{Fiber} = \alpha \times L = 0.25 \text{ dB/km} \times 185 \text{ km} = 46.25 \text{ dB}$$
* **Splice Loss ($L_{Splice}$):**
    $$L_{Splice} = N_S \times L_S = 46 \times 0.1 \text{ dB/splice} = 4.6 \text{ dB}$$
* **Connector Loss ($L_{Connector}$):**
    $$L_{Connector} = N_C \times L_C = 2 \times 0.2 \text{ dB/connector} = 0.4 \text{ dB}$$
* **Total Channel Loss ($L_{Total}$):**
    $$L_{Total} = 46.25 \text{ dB} + 4.6 \text{ dB} + 0.4 \text{ dB} = \mathbf{51.25 \text{ dB}}$$

**3. Calculate Power Margin ($P_M$):**
The power margin is the extra power (safety margin) remaining after accounting for all losses. A system is good if $P_M > 0$.
$$P_M = P_B - L_{Total}$$
$$P_M = 28 \text{ dB} - 51.25 \text{ dB} = \mathbf{-23.25 \text{ dB}}$$

**Conclusion:**
The Power Margin is **$-23.25 \text{ dB}$**, which is a **negative** value. Therefore, **this system is NOT good**. The total power loss in the link ($51.25 \text{ dB}$) is much higher than the maximum loss the system can tolerate ($28 \text{ dB}$). The signal would be received below the receiver's sensitivity, leading to an unacceptable Bit Error Rate (BER) or failure to operate.

***

### 5(b) Generalized Model of Digital Communications System

The generalized model of a digital communication system shows the process of converting a message into a digital format, transmitting it, and recovering it at the destination.


| Block | Working Explanation |
| :--- | :--- |
| **Information Source** | Generates the message (e.g., voice, text, image). |
| **Source Transducer** | Converts the non-electrical message into an electrical signal (e.g., microphone for voice). |
| **A/D Converter** | Converts the analog electrical signal into a digital bit stream (PCM process: Sampling, Quantization, Encoding). |
| **Transmitter** | **Channel Coding, Digital Modulation** is performed to match the signal to the channel characteristics and prepare it for transmission. |
| **Channel** | The physical medium (e.g., fiber, air, copper) through which the signal travels, where it is subjected to noise and attenuation. |
| **Receiver** | Performs the reverse operations: **Digital Demodulation** and **Channel Decoding** to reconstruct the original bit stream. |
| **D/A Converter** | Converts the digital bit stream back into an analog electrical signal. |
| **Output Transducer** | Converts the electrical signal back into the original message form (e.g., speaker for voice). |

**Elements to Add in the Transmitter and Why:**

The model above typically includes the most essential blocks. If instructed to add other elements to the transmitter section, the most critical blocks for performance and efficiency are the **Source Encoder** and the **Channel Encoder**:

1.  **Source Encoder (Data Compression)**
    * **Element:** Placed between the A/D Converter and the Channel Encoder.
    * **Reason:** Its purpose is to **reduce redundancy** in the digital stream (e.g., removing silent pauses in speech or predictable patterns in an image). This **increases the data rate-distance product** by allowing more information to be transmitted with fewer bits, improving channel efficiency. Examples include Huffman or LZW coding.

2.  **Channel Encoder (Error Control Coding)**
    * **Element:** Placed after the Source Encoder but before Digital Modulation.
    * **Reason:** Its purpose is to **introduce controlled redundancy** to the data stream. This redundancy, in the form of parity bits, allows the receiver to **detect and/or correct errors** caused by noise in the channel, significantly improving the link's reliability and Bit Error Rate (BER). Examples include Hamming codes or Cyclic Redundancy Check (CRC).
