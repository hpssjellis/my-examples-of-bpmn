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
