# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.
## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.
## POLICY EVALUATION FUNCTION
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V=np.zeros(len(P))
      for s in range(len(P)):
        for prob,next_state,reward,done in P[s][pi(s)]:
           V[s]+=prob*(reward+gamma *prev_V[next_state]*(not done))
      if np.max(np.abs(prev_V-V))<theta:
        break
      prev_V=V.copy()
    return V
```
## OUTPUT:
![Screenshot 2025-04-07 094301](https://github.com/user-attachments/assets/458412a6-da36-4f39-90f3-d50e41efea5f)
![Screenshot 2025-04-07 094450](https://github.com/user-attachments/assets/5c3c5d81-36a6-482e-9042-15da5057480c)
## State vaue function:
![Screenshot 2025-04-07 094554](https://github.com/user-attachments/assets/f101f789-495c-452f-b5d6-d5d4791df51e)
![Screenshot 2025-04-07 094625](https://github.com/user-attachments/assets/193cc5db-37e3-402a-9ccd-2fd599cc3631)

## Best policy:
![Screenshot 2025-04-07 094758](https://github.com/user-attachments/assets/9d318176-11dd-4385-b605-8e7ba25d0f9c)


## RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.

