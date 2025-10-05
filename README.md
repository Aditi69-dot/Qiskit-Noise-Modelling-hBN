# Qiskit-Noise-Modelling-hBN
Exploration of memristor behaviour under material specific (hBN) noise model in Qiskit.
# Qiskit Simulation of a Noisy Memristor based on hBN 
This is a simulation of a noisy memristor. It  has a single qubit quantum memory ceell whose functionality mimics the resistive switching behaviour of a memristor. The classical loop implemented here incorporated the noise parameters of Heaxgonal Boron Nitride (hBN) that I have obtained from literature review. 
## Objective
The objective of this was to study the effect of noise on resistive switching behavious.
## The Memristor model
In this model,the angle θ is analogous to the voltage/current pulse that attempts to write or read the memory.The measured outcome (0 or 1) is analogous to the device's instantaneous conductance/resistance (High Resistance State (HRS) for 0, Low Resistance State (LRS) for 1).The loop itself ensures the system exhibits "memory," where the resistance (0/1 state) is dependent on the history (the previous 0/1 state).
### Quantum Circuit:
It is a very simple single-qubit circuit wherin the qubit starts in ground state |0> and upon applying of the Ry gate is rotated by an angle theta along Y axis which puts it in a superposition state of |0> or |1> which upon measuremtn collapses to a definitive state of 0 or 1.
### Classical loop:
The outcome of the measurement of quantum circuit is fed back to the next input which is then stored as a new state. This state then determines the next pulse or the rotatin angle theta which is used for next iteration.
## Noise Model
The noise parameters of hBN were used which affected the outcome by directly introducing errors and decoherence into the quantum circuits operations which makes the observed switching behavior of memristor more random and less reliable than the ideal one.
### Errors applied:
The 2 types of errros introduced were:
1. Depolarizing Error: Applied to the Ry(θ) gate to model gate fidelity loss and increase randomness.
2. Thermal Relaxation Error (T1 and T2): Applied during measurement to model decoherence and energy decay, particularly biasing the state towards ∣0⟩ if T1 is short. 
## Conclusion
The simulation successfully demonstrated a quantum-inspired memristive effect where the measured state (0 or 1) dictates the control input (θ) for the next step. The output plot clearly shows the system operating in two distinct regimes: the High Resistance State (HRS / 0) and the Low Resistance State (LRS / 1), with the applied angle switching between π/3 and 2π/3 accordingly.

More importantl;y, the integration of hBN specific noise parameters (T1 n T2 and Depolarizing Error) introduces randomness into the switching. This noise prevents the system from getting perfectly stuck in one state ensuring constant although random transitions between the HRS and LRS. 
