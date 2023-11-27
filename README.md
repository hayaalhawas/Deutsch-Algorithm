# Quantum Task : Deutsch Algorithm

## Introduction 🌌

Deutsch's algorithm solves the parity problem for the special case that n=1. In the context of quantum computing, this problem is sometimes referred to as Deutsch's problem, 
quantum algorithms, 

If we view the input function f in Deutsch's problem as representing random access to a string, we're thinking about a two-bit string:  f(0)f(1)

    function     string      

      f1            00
  
      f2            01
  
      f3            10
  
      f4            11
​
 

The problem Deutsch’s algorithm tackles can now be stated as follows. Given a block box Uf implementing
some unknown function, determine whether the function is “constant” or “balanced”. Here,
constant means f always outputs the same bit, i.e. f(0) = f(1), and balanced means f outputs different bits
on different inputs, i.e. f(0) /= f(1).

![QD](https://github.com/hayaalhawas/Deutsch-Algorithm/assets/109044183/2f69efa0-50e6-40ec-bf8b-9cb50799a079)


Deutsch’s algorithm serves as an excellent proof of concept that, in certain settings, quantum computers are
strictly more powerful than classical ones. 
## Task 📝

In this task, embark on a hands-on Qiskit journey, where you'll delve into implementing the four oracles in the Deutsch algorithm. You'll then engage in the challenge of identifying the specific state of the oracle that was chosen randomly by your code based on the measurement of your circuit.

- Constant one
- Constant Zero
- Balnced One
- Balnced Zero






