# Quantum Computer Simulator

This project is a Quantum Computer Simulator that uses Python to mimic results of a physical Quantum Computer. The program takes in a QASM file, returns the final state vector, and plots measurement results. 

## How To Use This Simulator
### The following Quantum logic gates are implemented in this simulator:
* __I__ - Identity (I)
* __X__ - Pauli-X (X)
* __Y__ - Pauli-Y (Y)
* __Z__ - Pauli-Z (Y)
* __H__ - Hadamard (H)
* __S__ - Phase (S, P)
* __S<sup>†</sup>__ - Conjugate Transpose of S
* __T__ - π/8 (T)
* __T<sup>†</sup>__ - Conjugate Transpose of T
* __CX__ - Controlled Not (CNOT, CX)
* __U__ - Custom Unitary

### Creating and Using a QASM file
This program reads in a QASM file to create the initial state and apply the relevant gates. QASM (Quantum Assembly Language) is a low-level language used to program Quantum Computers. 
[IBM Quantum Composer](https://quantum.ibm.com/composer/files/new) allows you to visually create a circuit using logic blocks that can be exported as a QASM file. Simply paste the file path into the program and run the main cell to recieve the results of the experiment.

> [!NOTE]
> * The first 2 lines of IBM's QASM file contain the version and a library inculsion. These are followed by a blank space. For simplicity, leave these in the file and don't include any other spaces in the QASM file.
> * The Unitary gate by default has π/2 for the Theta, Phi, and Lambda parameters. For this program, make sure the parameters are decimal or float numbers

## Implementation details
This program uses [Kronecker products](https://en.wikipedia.org/wiki/Kronecker_product) to create a quantum state and apply gate transformations to it. This was done to accommodate for the __CNOT__ gate which entangles 2 Qubits, and therefore makes it impossible to represent them as seperable qubit vectors.

The simulator also simulates noise that is seen in real-world experiments. Change the value of the noise parameter from the default 0.01 to experience higher or lower noise in the data's results. Noise is experienced in the measuring portion of the program and it is done to mimic the dark counts experienced by physical qubit measurement apparatus.

The simulator already applies a computational basis measurement to each qubit at the end. Therefore, it is not needed to add measurement gates in the Quantum Composer circuit or QASM file.

## Acknowledgements and Additional Information
This project was the final project for the ___Quantum Computing I___ stream of the ___UT Austin Freshman Research Initiative___.
Below is a link to a presentation that includes an overview of the project, experimental results, and a comparison to IBM's simulator results.
[https://docs.google.com/presentation/d/1PQq5UbhUgi7Pp6gAufiHn1PWFwyILQEj3BDO-2yfxKE/edit?usp=sharing](url)

