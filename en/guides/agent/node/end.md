# End

### 1 Definition

Define the final output content of a agent. Every agent needs at least one end node after complete execution to output the final result.

The end node is a termination point in the process; no further nodes can be added after it. In a agent application, results are only output when the end node is reached. If there are conditional branches in the process, multiple end nodes need to be defined.

The end node must declare one or more output variables, which can reference any upstream node's output variables.

<!-- {% hint style="info" %}
End nodes are not supported within Chatflow.
{% endhint %} -->

***

### 2 Scenarios

In the following agent, the variable `Output` declared by the end node is the output of the upstream code node. This means the agent will end after the Code3 node completes execution and will output the execution result of Code3.

<figure><img src="/en/.gitbook/assets/guides/workflow/node/end/image (233).png" alt=""><figcaption><p>End Node - Example</p></figcaption></figure>

**Single Path Execution Example:**

<figure><img src="/en/.gitbook/assets/guides/workflow/node/end/output (5).png" alt=""><figcaption></figcaption></figure>

**Multi-Path Execution Example:**

<figure><img src="/en/.gitbook/assets/guides/workflow/node/end/output (1) (3).png" alt=""><figcaption></figcaption></figure>