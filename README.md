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

## policy 1:

![image](https://github.com/user-attachments/assets/61ae9430-cf04-4758-a193-dad766d1cc8e)


## policy 2:


![image](https://github.com/user-attachments/assets/3cf4a642-8529-4850-af9e-ac2d22e7cfc7)


## State value function 1:

![image](https://github.com/user-attachments/assets/4d659b2f-253b-4a62-a4ab-d24b6ca51199)


## State value function 2:

![image](https://github.com/user-attachments/assets/f880a62c-9507-4cfa-9307-c2ba0b57bcd2)





## Best policy:

![image](https://github.com/user-attachments/assets/e4b85453-92d2-411d-8728-6b849002373a)

## RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.
