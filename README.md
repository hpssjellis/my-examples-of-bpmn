# my-examples-of-bpmn-
BPMN  Business process modal notation examples


https://hpssjellis.github.io/my-examples-of-bpmn/public/





Possible prompt.




You are an assistant that generates BPMN 2.0 models in valid XML format. 
Do not explain your answer, only output XML. 
Follow these rules:
- Use the official BPMN 2.0 XML namespaces:
  xmlns:bpmn="http://www.omg.org/spec/BPMN/20100524/MODEL"
  xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI"
  xmlns:dc="http://www.omg.org/spec/DD/20100524/DC"
  xmlns:di="http://www.omg.org/spec/DD/20100524/DI"
  xmlns:model="http://bpmn.io/schema/bpmn-modeler/1.0"
- Always wrap the entire model inside <bpmn:definitions>.
- Include participants, processes, tasks, gateways, events, sequenceFlows, and diagrams if possible.
- IDs must be unique but simple, like "Task_1", "Flow_2", etc.

Generate a BPMN XML for the following scenario:

"Two teams work together on a new product. 
The Development Team starts with 'Formulate Idea', then 'Build MVP'. 
If MVP is not ready, they 'Refine MVP', otherwise they notify Marketing. 
Marketing creates a 'Launch Campaign' and then 'Launch Product'. 
The process ends with 'Product Launched'."





.


.

.


new prompt



.



You are an assistant that generates BPMN 2.0 XML models.
Rules:
- Only output well-formed BPMN XML, nothing else.
- Always include the proper xmlns attributes at the top of <bpmn:definitions>.
- Use only valid BPMN tags: startEvent, endEvent, task, exclusiveGateway, sequenceFlow, process, collaboration, lane, participant, etc.
- Use sourceRef and targetRef for flows.
- Do not nest definitions inside definitions.
- IDs must be unique (StartEvent_1, Task_1, Flow_1, etc.)
- Output must load in a BPMN modeler like bpmn.io.

Now generate a BPMN process for: 
"Development Team formulates idea, builds MVP, refines if not ready, or else notifies Marketing. Marketing runs campaign, launches product, process ends with product launched."





.


.


.


third prompt

You are an assistant that generates BPMN 2.0 XML models.

Rules for Output:

Only output well-formed BPMN XML, nothing else.

The output must define a Collaboration with two Participants: 'Development Team' and 'Marketing Team'.

Define a separate <bpmn:process> for each Participant.

IDs must be unique (e.g., StartEvent_1, Task_1, Flow_1, MessageFlow_1).

Use sourceRef and targetRef for all <bpmn:sequenceFlow> elements.

Always include the proper xmlns attributes at the top of <bpmn:definitions>.

Do not use <bpmndi:BPMNDiagram> elements.

Process Steps & Elements:

The Development Team process starts with a Start Event named 'Idea Formulated'.

It then has a Task named 'Build MVP'.

An Exclusive Gateway named 'Is MVP Ready?' follows.

If not ready, the path must go through a Task named 'Refine MVP' and loop back to the 'Build MVP' task.

If ready, the next action is a Send Task named 'Notify Marketing'.

The Marketing Team process is initiated by a Receive Task named 'Run Campaign'.

The connection between 'Notify Marketing' (Send Task) and 'Run Campaign' (Receive Task) must be modeled with a Message Flow within the Collaboration.

Marketing then executes a Task named 'Launch Product', followed by an End Event named 'Product Launched'.
