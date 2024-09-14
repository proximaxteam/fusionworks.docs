# Start

### Definition

Define the initial parameters for starting a agent.

You can customize the input variables for initiating the agent in the start node. Every agent requires a start node.

<figure><img src="/en/.gitbook/assets/guides/workflow/node/start/image (236).png" alt="" width="375"><figcaption><p>Agent Start Node</p></figcaption></figure>

The start node supports defining input variables of four types:

* Text
* Paragraph
* Dropdown Options
* Number

<figure><img src="/en/.gitbook/assets/guides/workflow/node/start/output (2) (1).png" alt=""><figcaption><p>Configure Start Node Variables</p></figcaption></figure>

Once configured, the agent will prompt for the values of the variables defined in the start node during execution.

<figure><img src="/en/.gitbook/assets/guides/workflow/node/start/output (3) (1).png" alt=""><figcaption></figcaption></figure>

<!-- {% hint style="info" %}
Tip: In Chatflow, the start node provides built-in system variables: `sys.query` and `sys.files`.

`sys.query` is used for user input questions in conversational applications.

`sys.files` is used for file uploads in conversations, such as uploading an image, which needs to be used in conjunction with an image understanding model.
{% endhint %} -->