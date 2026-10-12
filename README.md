# QuantumShield: Detecting Eavesdropping with Qiskit

## Overview

QuantumShield is an educational proof of concept that simulates the BB84 quantum key distribution protocol using IBM Qiskit. It investigates whether an intercept-resend eavesdropping attack can be detected through changes in the Quantum Bit Error Rate (QBER).

## Problem Statement

Secure communication requires a way to detect interference during key exchange. BB84 uses quantum states and measurements in different bases to make certain interception attempts detectable.

## Objectives

- Simulate BB84 qubit preparation and measurement.
- Implement an intercept-resend attack.
- Compare a normal channel with an attacked channel.
- Measure QBER on the sifted key.
- Evaluate the results using an ideal quantum simulation.

## Methodology

1. Alice generates random bits and preparation bases.
2. Bob independently chooses measurement bases.
3. Alice and Bob retain positions where their bases match.
4. In the attacked scenario, Eve measures each qubit using a random basis and resends the measured state.
5. QBER is calculated by comparing the sifted bits held by Alice and Bob.
6. Multiple trials are used to examine observed error rates.

## Technology Stack

- Python
- IBM Qiskit
- NumPy
- Matplotlib
- Pandas

## Experimental Results

- Trials per scenario: 20
- Bits transmitted per trial: 1,000
- Mean QBER without eavesdropping: See `quantumshield_results.csv`.
- Mean QBER with intercept-resend: See `quantumshield_results.csv`.

Under ideal BB84 assumptions, the expected QBER is approximately 0% without interception and 25% under a full intercept-resend attack on the sifted key. Actual simulation measurements are provided in the results CSV and should be compared against these expectations.

## Limitations

This project uses ideal statevector simulation rather than physical quantum hardware. It does not implement a complete production-ready secure communication system or account for realistic hardware noise and all security requirements.

## Reproducibility

Open `QuantumShield_BB84.ipynb` in Google Colab, install the required dependencies, and run the notebook cells in order.

## Future Scope

- Introduce realistic quantum noise models.
- Investigate partial interception.
- Study finite-key effects and error mitigation.
- Explore execution on quantum hardware.

## Disclaimer

QuantumShield is an educational simulation and is not intended to protect real-world communications.
