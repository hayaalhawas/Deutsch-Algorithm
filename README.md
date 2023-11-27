# Quantum Task : Deutsch Algorithm

## Introduction 🌌

Logic gates, the bedrock of digital circuits, wield their significance across both classical and quantum computing realms. These gates empower us to manipulate binary inputs (0s and 1s) to unveil specific outputs, laying the foundation for intricate computations and discerning decision-making.

## Task 📝

In this task Immerse in practical Qiskit experience, you are required to implement a the 4 cases in the Deutsch Algorithm 
- Constant one
- Constant Zero
- Balnced One
- Balnced Zero

<img width="429" alt="image" src="https://github.com/hayaalhawas/Deutsch-Algorithm/assets/109044183/2d8ee080-0026-4815-93af-dafc1d42b693">


https://people.vcu.edu/~sgharibian/courses/CMSC491/notes/Lecture%206%20-%20Deutsch's%20algorithm.pdf
### Steps:
1. by Study the Deutsch algorithm you understand its working.
2. Design a quantum circuit to create a balanced oracle for the problem.
3. Clearly explain the design choices and the reasoning behind them in your code comments.
4. Test the oracle using various inputs to verify its balanced behavior.

## Task 2: Signing Up for IBM Quantum Lab and Using Python Notebook

In this task, you will sign up for IBM Quantum Lab and utilize a Python notebook for the given problem.


from qiskit import QuantumCircuit, BasicAer, Aer, execute
from random import choice
qb = QuantumCircuit(2,1)
qb.x(1)

def constent_zero(q):
    q.i(0)
    q.i(1)
    
def constent_one(q):
    q.i(0)
    q.x(1)
    
def balanced_1(q):
    q.cx(0, 1)
    
def balanced_2(q):
    q.cx(0, 1)
    q.x(0)

def deutsh():     
    funactioList = [balanced_1, balanced_2, constent_one, constent_zero]
    qb.h(0)
    qb.h(1)
    qb.barrier()
    choice(funactioList)(qb)
    constent_zero(qb)
    qb.barrier()
    qb.h(0)
    qb.measure(1, 0)
    
    job = execute(qb, Aer.get_backend('qasm_simulator'))
    output = job.result().get_counts()
    print(output)
    if output.get('1') == 1 or output.get('0')==1:
        print("balenced")
    elif output.get('1')==0 or output.get('0')==0:
        print("constent")
    qb.draw("mpl")
    
deutsh()
