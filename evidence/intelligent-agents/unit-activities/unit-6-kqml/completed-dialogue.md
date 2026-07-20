# Unit 6 Activity – KQML and KIF Agent Dialogue

## Activity Overview

This activity demonstrates a simple dialogue between two software agents using **KQML performatives** and **KIF-style knowledge representation**.

The objective was to practise how intelligent agents communicate by exchanging structured messages rather than simply calling functions or APIs.

## Scenario

Two software agents communicate with each other:

- **Alice** – Procurement Agent
- **Bob** – Warehouse Stock-Control Agent

Alice needs to determine:

1. Whether 50-inch televisions are currently available.
2. How many HDMI ports the televisions have.

---

## Message 1 – Alice asks about stock availability

```lisp
(ask-one
    :sender Alice
    :receiver Bob
    :language KIF
    :ontology warehouse-inventory
    :content
        (available-stock television-50-inch ?quantity)
)
```

### Meaning

Alice asks Bob to provide the quantity of available 50-inch televisions.

---

## Message 2 – Bob replies with the stock quantity

```lisp
(tell
    :sender Bob
    :receiver Alice
    :language KIF
    :ontology warehouse-inventory
    :content
        (= (available-stock television-50-inch) 24)
)
```

### Meaning

Bob informs Alice that **24 televisions** are currently available.

---

## Message 3 – Alice asks about HDMI ports

```lisp
(ask-one
    :sender Alice
    :receiver Bob
    :language KIF
    :ontology product-specification
    :content
        (hdmi-port-count television-50-inch ?ports)
)
```

### Meaning

Alice asks Bob how many HDMI ports the television has.

---

## Message 4 – Bob replies with the specification

```lisp
(tell
    :sender Bob
    :receiver Alice
    :language KIF
    :ontology product-specification
    :content
        (= (hdmi-port-count television-50-inch) 4)
)
```

### Meaning

Bob informs Alice that the television has **4 HDMI ports**.

---

## Message 5 – Alice confirms receipt

```lisp
(reply
    :sender Alice
    :receiver Bob
    :language KIF
    :ontology procurement
    :content
        (information-received
            television-50-inch
            (available-stock 24)
            (hdmi-port-count 4)
        )
)
```

### Meaning

Alice confirms that she has successfully received both the stock availability and the product specification.

---

## Dialogue Summary

This dialogue demonstrates the use of:

- **KQML performatives** (`ask-one`, `tell`, and `reply`) to define the purpose of each message.
- **KIF-style expressions** to represent the knowledge exchanged between agents.
- A **shared ontology** so that both agents interpret terms such as `available-stock` and `hdmi-port-count` consistently.

> **Note:** The values used in this example (24 televisions and 4 HDMI ports) are illustrative and were created for this learning activity.