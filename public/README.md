




prompt to try 

"Please generate a BPMN 2.0 XML diagram that models the process of a new technology startup launching a product. The diagram should be a single XML code block. Include the following elements: A Start Event named 'Idea Formulation'. A Lane named 'Development Team' with a Task named 'Build MVP'. A second Lane named 'Marketing Team' with a Task named 'Create Launch Campaign'. An Exclusive Gateway named 'Is MVP Ready?' that connects to two different Sequence Flows. Two additional Tasks for each of the two outcomes from the gateway (one for 'Refine MVP', one for 'Launch Product'). An End Event named 'Product Launched'."




generated 


<?xml version="1.0" encoding="UTF-8"?>
<bpmn2:definitions xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:bpmn2="http://www.omg.org/spec/BPMN/20100524/MODEL" xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI" xmlns:dc="http://www.omg.org/spec/DD/20100524/DC" xmlns:di="http://www.omg.org/spec/DD/20100524/DI" id="sample-diagram" targetNamespace="http://bpmn.io/schema/bpmn">
  <bpmn2:process id="Process_1" isExecutable="false">
    <bpmn2:laneSet id="LaneSet_1">
      <bpmn2:lane id="Lane_1" name="Development Team">
        <bpmn2:flowNodeRef>StartEvent_1</bpmn2:flowNodeRef>
        <bpmn2:flowNodeRef>Task_1</bpmn2:flowNodeRef>
        <bpmn2:flowNodeRef>ExclusiveGateway_1</bpmn2:flowNodeRef>
        <bpmn2:flowNodeRef>Task_2</bpmn2:flowNodeRef>
      </bpmn2:lane>
      <bpmn2:lane id="Lane_2" name="Marketing Team">
        <bpmn2:flowNodeRef>Task_3</bpmn2:flowNodeRef>
        <bpmn2:flowNodeRef>Task_4</bpmn2:flowNodeRef>
        <bpmn2:flowNodeRef>EndEvent_1</bpmn2:flowNodeRef>
      </bpmn2:lane>
    </bpmn2:laneSet>
    <bpmn2:startEvent id="StartEvent_1" name="Idea Formulation">
      <bpmn2:outgoing>SequenceFlow_1</bpmn2:outgoing>
    </bpmn2:startEvent>
    <bpmn2:task id="Task_1" name="Build MVP">
      <bpmn2:incoming>SequenceFlow_1</bpmn2:incoming>
      <bpmn2:outgoing>SequenceFlow_2</bpmn2:outgoing>
    </bpmn2:task>
    <bpmn2:exclusiveGateway id="ExclusiveGateway_1" name="Is MVP Ready?">
      <bpmn2:incoming>SequenceFlow_2</bpmn2:incoming>
      <bpmn2:outgoing>SequenceFlow_3</bpmn2:outgoing>
      <bpmn2:outgoing>SequenceFlow_4</bpmn2:outgoing>
    </bpmn2:exclusiveGateway>
    <bpmn2:task id="Task_2" name="Refine MVP">
      <bpmn2:incoming>SequenceFlow_3</bpmn2:incoming>
      <bpmn2:outgoing>SequenceFlow_5</bpmn2:outgoing>
    </bpmn2:task>
    <bpmn2:task id="Task_3" name="Create Launch Campaign">
      <bpmn2:incoming>SequenceFlow_5</bpmn2:incoming>
      <bpmn2:incoming>SequenceFlow_4</bpmn2:incoming>
      <bpmn2:outgoing>SequenceFlow_6</bpmn2:outgoing>
    </bpmn2:task>
    <bpmn2:task id="Task_4" name="Launch Product">
      <bpmn2:incoming>SequenceFlow_6</bpmn2:incoming>
      <bpmn2:outgoing>SequenceFlow_7</bpmn2:outgoing>
    </bpmn2:task>
    <bpmn2:endEvent id="EndEvent_1" name="Product Launched">
      <bpmn2:incoming>SequenceFlow_7</bpmn2:incoming>
    </bpmn2:endEvent>
    <bpmn2:sequenceFlow id="SequenceFlow_1" sourceRef="StartEvent_1" targetRef="Task_1" />
    <bpmn2:sequenceFlow id="SequenceFlow_2" sourceRef="Task_1" targetRef="ExclusiveGateway_1" />
    <bpmn2:sequenceFlow id="SequenceFlow_3" name="No" sourceRef="ExclusiveGateway_1" targetRef="Task_2" />
    <bpmn2:sequenceFlow id="SequenceFlow_4" name="Yes" sourceRef="ExclusiveGateway_1" targetRef="Task_3" />
    <bpmn2:sequenceFlow id="SequenceFlow_5" sourceRef="Task_2" targetRef="Task_3" />
    <bpmn2:sequenceFlow id="SequenceFlow_6" sourceRef="Task_3" targetRef="Task_4" />
    <bpmn2:sequenceFlow id="SequenceFlow_7" sourceRef="Task_4" targetRef="EndEvent_1" />
  </bpmn2:process>
  <bpmndi:BPMNDiagram id="BPMNDiagram_1">
    <bpmndi:BPMNPlane id="BPMNPlane_1" bpmnElement="Process_1">
      <bpmndi:BPMNShape id="BPMNShape_Lane_1" bpmnElement="Lane_1">
        <dc:Bounds x="160" y="80" width="800" height="200" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_Lane_2" bpmnElement="Lane_2">
        <dc:Bounds x="160" y="280" width="800" height="200" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_StartEvent_1" bpmnElement="StartEvent_1">
        <dc:Bounds x="212" y="162" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="195" y="205" width="70" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_Task_1" bpmnElement="Task_1">
        <dc:Bounds x="300" y="140" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_ExclusiveGateway_1" bpmnElement="ExclusiveGateway_1" isMarkerVisible="true">
        <dc:Bounds x="465" y="155" width="50" height="50" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="446" y="212" width="88" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_Task_2" bpmnElement="Task_2">
        <dc:Bounds x="590" y="140" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_Task_3" bpmnElement="Task_3">
        <dc:Bounds x="590" y="320" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_Task_4" bpmnElement="Task_4">
        <dc:Bounds x="760" y="320" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="BPMNShape_EndEvent_1" bpmnElement="EndEvent_1">
        <dc:Bounds x="912" y="342" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="892" y="385" width="77" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNEdge id="BPMNEdge_SequenceFlow_1" bpmnElement="SequenceFlow_1">
        <di:waypoint x="248" y="180" />
        <di:waypoint x="300" y="180" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="BPMNEdge_SequenceFlow_2" bpmnElement="SequenceFlow_2">
        <di:waypoint x="400" y="180" />
        <di:waypoint x="465" y="180" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="BPMNEdge_SequenceFlow_3" bpmnElement="SequenceFlow_3">
        <di:waypoint x="515" y="180" />
        <di:waypoint x="590" y="180" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="530" y="162" width="17" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="BPMNEdge_SequenceFlow_4" bpmnElement="SequenceFlow_4">
        <di:waypoint x="490" y="205" />
        <di:waypoint x="490" y="360" />
        <di:waypoint x="590" y="360" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="499" y="280" width="18" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="BPMNEdge_SequenceFlow_5" bpmnElement="SequenceFlow_5">
        <di:waypoint x="640" y="220" />
        <di:waypoint x="640" y="320" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="BPMNEdge_SequenceFlow_6" bpmnElement="SequenceFlow_6">
        <di:waypoint x="690" y="360" />
        <di:waypoint x="760" y="360" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="BPMNEdge_SequenceFlow_7" bpmnElement="SequenceFlow_7">
        <di:waypoint x="860" y="360" />
        <di:waypoint x="912" y="360" />
      </bpmndi:BPMNEdge>
    </bpmndi:BPMNPlane>
  </bpmndi:BPMNDiagram>
</bpmn2:definitions>
