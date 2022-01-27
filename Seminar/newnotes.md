The availability KPIs measure the percentage of time during which the network cells
have not been available. According to 3GPP, one cell is considered to be available
when eNodeB can offer E-RAB services in that particular cell.
The E-UTRAN Cell Availability measures the percentage of time in order to evaluate
the service degradation and the network performance. This parameter can be measured
in the cluster level (eq. 7).
Availability ¼ meas:  PRRU:CellUnavailableT
Measperiod
 100%


 https://link.springer.com/content/pdf/10.1007%2F978-3-030-23976-3.pdf





 What Is the Difference Between Stochastic and Deterministic Models?
Unlike deterministic models that produce the same exact results for a particular set of inputs, stochastic models are the opposite; the model presents data and predicts outcomes that account for certain levels of unpredictability or randomness. TSt
---------------------------------------------------------------------------


#### POWER LINE COMMUNICATIONS:

#### Intro to PLCs

https://www.sciencedirect.com/topics/engineering/power-line

Power line carrier (PLC) communication technology transmits data through the power line. The PLC technology is making use of high-voltage power lines (10 kV or above, and low-voltage power lines 220 or 380 V) for the development and promotion of remote meter reading. The use of PLC is expanding into the distribution lines for load control and even into households to control lighting, alarm systems and air conditioning and heating. The main application, however, is protective relaying for transmission lines. A channel is used in line protection so that both ends of a circuit are cleared at high speed for all types of faults, including end zone faults. A PLC channel also can be used to provide remote tripping functions for power transformer protection, shunt reactor protection, and remote breaker failure relaying.

The main advantage of PLC is eliminating the difficulty of installing additional dedicated communication cables. The disadvantages of PLC are obvious, too. The power line is a very bad channel for communication, mainly because of interference and signal attenuation. Interference comes from power electronic devices, low-voltage load, switch operation, and broadcast signals. In such a noisy environment, it is difficult to ensure data quality. Signal attenuation is brought about by the complicated structure of the power grid, which gives signals multiple transmission paths. The power line communication environment, therefore, is too severe to ensure reliability and stability. The solar PV power station has many power electronic devices, such as inverter, static var compensator, and static var generator. These devices arouse harmonic interference into the AC power line, so PLC should not be used on the AC power line. The DC power line between PV convergence box and inverter, however, has less interference and a single transmission path, and can implement PLC technology.

https://www.eetimes.com/what-is-power-line-communication/

Power Line Communication (PLC) is a communication technology that enables sending data over existing power cables. This means that, with just power cables running to an electronic device (for example) one can both power it up and at the same time control/retrieve data from it in a half-duplex manner.

PLC Market: Overview

Segments

For the purpose of understanding, PLC can be broadly viewed as:

1. Narrowband PLC

2. Broadband PLC

Narrowband PLC works at lower frequencies (3-500 kHz), lower data rates (up to 100s of kbps), and has longer range (up to several kilometers), which can be extended using repeaters. Broadband PLC works at higher frequencies (1.8-250 MHz), high data rates (up to 100s of Mbps) and is used in shorter-range applications.

Recently, narrowband Power Line Communication has been receiving widespread attention due to its applications in the Smart Grid. Another application that narrowband PLC has been used in is smart energy generation, particularly in micro-inverters for solar panels.

Broadband PLC, in contrast, has mainly found acceptance as a last-mile solution for Internet distribution and home networking. With its high data rates and no additional wiring, broadband PLC is seen as an exciting and effective technology for multimedia distribution within homes. This optimism in the market is reflected by the recent acquisitions of Intellon by Atheros, Coppergate by Sigma, DS2 by Marvell, and Gigle by Broadcom, all in the Home Area Networking (HAN) segment.

There is another way to classify Power Line Communication and that is:

1. PLC over AC lines

2. PLC over DC lines

While most companies are currently geared towards providing AC-PLC solutions, PLC in DC lines also has applications. Two such applications are PLC over the DC-bus in distributed energy generation, and PLC in transportation (electronic controls in airplanes, automobiles and trains). This use reduces wiring complexity, weight, and ultimately cost of communications inside vehicles. However, in this article, we will be dealing mostly with narrowband PLC over AC lines.

PLC is like any other communication technology whereby a sender modulates the data to be sent, injects it onto medium, and the receiver de-modulates the data to read it. The major difference is that PLC does not need extra cabling, it re-uses existing wiring. Considering the pervasiveness of power lines, this means with PLC, virtually all line- powered devices can be controlled or monitored!

When discussing communication technology, it is often useful to refer to the 7-layer OSI model. Some PLC chips can implement only the Physical Layer of the OSI model, while others integrate all seven layers. 

A variety of modulation schemes can be used in PLC. Some of these are Orthogonal Frequency Division Multiplexing (OFDM), Binary Phase Shift Keying (BPSK), Frequency Shift Keying (FSK), Spread-FSK (S-FSK) and proprietary schemes too (for example Differential Code Shift Keying (DCSK) from Yitran). In the table below, BPSK, FSK, SFSK and OFDM are compared on the basis of two important criteria – bandwidth efficiency and complexity (cost).


OFDM in particular offers high data rates, but requires computational horsepower to churn out Fast Fourier Transforms (FFT) and Inverse-FFT (IFFT), as required by the scheme. On the other hand, BPSK, FSK are robust and simple but offer lower data rates. The current trend is to move towards OFDM with PSK modulation (G3 and probably P1901.2). Such heavy computation will require DSP capability, whereas FSK, PSK and SFSK can be accomplished by a microcontroller.



file:///home/deopranav/Downloads/Performance_Analysis_of_Two_Case_Studies_for_a_Pow.pdf

Paper for failure modelling:

Power line communication (PLC) is a promising technique
for information transmission using existing power lines. PLC
technologies can be used in an inside-building low voltage
environment, a short-distance medium voltage environment,
or a long-distance high voltage environment. Mixed highvoltage, medium-voltage, and low-voltage power supply
networks could be bridged to form very large networks for
communications, as alternative telecommunication networks. 


Therefore, huge cost of running wires such as Ethernet in
many buildings can be saved. However, there are still lots of
challenges for implementation in reality. Since the power
line network has originally been designed for electricity
distribution, rather than for data transfer, the power line as
communication channel has various noise and disturbance
characteristics, resulting in an unreliable channel. Many
factors, such as channel attenuation, white noise, RF noise
from nearby radio transmitters, impulse noise from electrical
machines and relays, may cause the channel unreliability.