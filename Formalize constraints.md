# Task 2 — Formalize Constraints

Formalization means converting the system constraints into simple logical expressions. These expressions help the verification team check whether the system follows its safety rules.

---

## C1 — Barrier Must Not Open When a Train Is Present

**Formal Expression:**

`Train_Present &rarr; &not;Barrier_Open`

**Meaning:**  
If a train is present at the crossing, the barrier must not be open.

---

## C2 — Barrier Must Close When a Train Is Approaching

**Formal Expression:**

`Train_Approaching &rarr; Barrier_Closed`

**Meaning:**  
If a train is approaching the crossing, the barrier must be closed before the train reaches the crossing.

---

## C3 — Warning Signals Must Activate When a Train Approaches

**Formal Expression:**

`Train_Approaching &rarr; (Warning_Light_ON &and; Alarm_ON)`

**Meaning:**  
If a train is approaching, both the warning light and audible alarm must be ON.

---

## C4 — Barrier Must Remain Closed While the Train Is Passing

**Formal Expression:**

`Train_Passing &rarr; Barrier_Closed`

**Meaning:**  
If the train is passing through the crossing, the barrier must remain closed.

---

## C5 — Barrier Can Open Only After the Train Has Cleared

**Formal Expression:**

`Barrier_Open &rarr; Train_Cleared`

**Meaning:**  
If the barrier is open, the system must have confirmed that the train has completely cleared the crossing.

---

## C6 — Traffic Signal Must Show STOP When a Train Is Detected

**Formal Expression:**

`Train_Detected &rarr; Traffic_Signal_STOP`

**Meaning:**  
If a train is detected, the traffic signal must show **STOP** to road users.

---

## C7 — Sensor Failure Must Prevent Automatic Barrier Opening

**Formal Expression:**

`Sensor_Failure &rarr; &not;Automatic_Barrier_Open`

**Meaning:**  
If a train-detection sensor fails, the system must not automatically open the barrier.

---

## C8 — Communication Loss Must Put the Crossing Into a Safe State

**Formal Expression:**

`Communication_Lost &rarr; Safe_State`

**Meaning:**  
If communication with the control center is lost, the crossing must enter a safe condition.

---

## Logical Symbols Used

| **Symbol** | **Meaning** |
|---|---|
| `&rarr;` | Implies / If-Then |
| `&not;` | NOT / Must Not |
| `&and;` | AND / Both Conditions |
| `TRUE` | Condition is active or present |
| `FALSE` | Condition is inactive or not present |
