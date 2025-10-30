from qiskit import QuantumCircuit, transpile
from qiskit_aer import AerSimulator
from qiskit.visualization import plot_histogram
import matplotlib.pyplot as plt
import random

secret_bit = random.choice([0, 1])
print("Alice's secret bit:", secret_bit)

qc = QuantumCircuit(1, 1)

if secret_bit == 1:
    qc.x(0)

qc.measure(0, 0)

simulator = AerSimulator()
compiled_circuit = transpile(qc, simulator)
job = simulator.run(compiled_circuit, shots=100)
result = job.result()
counts = result.get_counts()

print("Bob's measurement results:", counts)

qc.draw('mpl')
plt.show()

plot_histogram(counts)
plt.show()
