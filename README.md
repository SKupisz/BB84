# BB84 - the quantum cryptography standard

The BB84 quantum protocol was created in 1984 by Charles Bennett and Gilles Brassard. 
The main difference in comparison to traditional cryptography used today is that while the traditional one relies on difficult mathematical problems, the BB84 is protected by the laws of quantum physics.

**How does this protocol work?**

Suppose we have two entities that want to communicate with each other - named Alice and Bob. 
They want to keep their secrets for themselves, so they need a secret to encrypt their messages

The question is - how to share it securely? The answer, in the quantum computing world, is - use the BB84 protocol!

The BB84 protocol relies on the following steps:
    
1. Alice chooses random bits and the corresponding base Z and X.
2. If a base of a particular bit is Z, Alice sends either `|0>` or `|1>`, corresponding to the value of the bit.
3. If a base of a particular bit is X, Alice applies the Hadamard gate i.e. sends either `|+>` or `|->`, depending on the bit's value being respectively 0 or 1
4. Bob chooses his base at random and performs the measurements the same way Alice applied Z and X.
5. Alice and Bob openly exchange their bits and compare them.
6. The matching bits create the secret key

**Why is it secure?**

The main reason why the exchange is secure is that the Eavesdropper cannot measure a qubit without changing its state (one of the fundamental principles of quantum computing being a direct consequence of quantum mechanics). Therefore, the eavesdropper must be lucky to listen to the entire key and now be caught - more precisely, the probability that Eavesdropper won't succeed is $P = 1 - (3/4)^n$, where n - number of shared qubits