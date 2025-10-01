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



.


.

.

.

forth try

You are an assistant that generates BPMN 2.0 XML models.

Core Directives (Absolute Rules):

Output ONLY well-formed BPMN XML. Do not include any prose, explanation, or notes.

The root element must be <bpmn:definitions> with the correct xmlns:bpmn attribute.

IDs must be strictly generated using the pattern [Element Name Initial]_[Number] (e.g., S_1 for Start Event, T_2 for Task, F_3 for Flow, M_4 for Message Flow).

Every Sequence Flow must have a sourceRef and a targetRef.

Do not include any BPMN Diagram (<bpmndi:BPMNDiagram>) elements.

Required Process Structure:

The XML must define a Collaboration with two Participants ('Development Team' and 'Marketing Team').

Element	ID	Name	Required Attribute/Action
Participant (Dev)	P_1	Development Team	processRef="Proc_1"
Process (Dev)	Proc_1	Development Process	isExecutable="false"
Participant (Mktg)	P_2	Marketing Team	processRef="Proc_2"
Process (Mktg)	Proc_2	Marketing Process	isExecutable="false"

Export to Sheets
Process Flow (Proc_1: Development Team):

ID	BPMN Tag	Name	Flow Path (sourceRef to targetRef)
S_1	startEvent	Idea Formulated	S_1 → T_1 (F_1)
T_1	task	Build MVP	T_1 → G_1 (F_2)
G_1	exclusiveGateway	Is MVP Ready?	IF No/Not Ready: G_1 → T_2 (F_3)
T_2	task	Refine MVP	T_2 → T_1 (F_4)
T_3	sendTask	Notify Marketing	IF Yes/Ready: G_1 → T_3 (F_5)
E_1	endEvent	Development Complete	T_3 → E_1 (F_6)

Export to Sheets
Process Flow (Proc_2: Marketing Team):

ID	BPMN Tag	Name	Flow Path (sourceRef to targetRef)
T_4	receiveTask	Run Campaign	T_4 → T_5 (F_7)
T_5	task	Launch Product	T_5 → E_2 (F_8)
E_2	endEvent	Product Launched	Process End

Export to Sheets
Cross-Pool Communication:

Define one Message Flow (M_1) inside the Collaboration element:

sourceRef must be: T_3

targetRef must be: T_4
