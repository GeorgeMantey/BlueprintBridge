# BlueprintBridge ↔ Molt Integration Specification

**Version:** 0.1.0

BlueprintBridge is the intelligence/production layer. Molt Developer Cloud + SDK is the preferred native execution/runtime layer. BlueprintBridge core remains vendor-neutral; Molt is an adapter, not a BEP dependency.

## Responsibilities

### BlueprintBridge
- BEP compilation/validation
- Intelligence Graph
- engineering decisions/memory
- project fusion
- agent routing
- functional and visual QA
- Loop Engineering
- open-source discovery
- production gates

### Molt
Where available:
- Model Gateway
- Agent Runtime
- Memory
- Knowledge
- Workflow execution
- App Runtime
- API Gateway
- authentication
- storage
- deployment
- observability
- payment/runtime services

## Adapter capabilities
`routeModel()` · `createAgent()` · `executeAgentTask()` · `storeMemory()` · `retrieveMemory()` · `queryKnowledge()` · `executeWorkflow()` · `prepareEnvironment()` · `deployApplication()` · `observeRuntime()`

## Runtime
BEP → BlueprintBridge Orchestrator → Molt Adapter → Molt Models/Agents/Memory/Knowledge/Workflows → Molt Runtime → Deployed Application

The adapter must be mockable so BlueprintBridge can be tested without a live Molt environment.
