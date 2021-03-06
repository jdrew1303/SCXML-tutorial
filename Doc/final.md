# [\<final\>](https://www.w3.org/TR/scxml/#final)
Represents a final state of an \<scxml\> or compound \<state\> element.

![final](https://user-images.githubusercontent.com/18611095/28068129-d5bdb836-664c-11e7-8655-f4a7e6ed9eeb.png)
```
<scxml name="Scxml" version="1.0" xmlns="http://www.w3.org/2005/07/scxml">
	<state id="Work">
		<transition event="done.state.Work" target="WorkFinished"/>
		<state id="CompletingTask">
			<transition target="Completed"/>
		</state>
		<final id="Completed"/>
	</state>
	<final id="WorkFinished"/>
</scxml>
```

## [W3C IRP tests](https://www.w3.org/Voice/2013/scxml-irp)

### [1. Test 372](https://www.w3.org/Voice/2013/scxml-irp/372/test372.txml)
When the state machine enters the final child of a state element, the SCXML processor MUST generate the event done.state.id after completion of the onentry elements, where id is the id of the parent state.

![test372](https://user-images.githubusercontent.com/18611095/28661582-d17ef33c-72bf-11e7-9b28-cd2ef7260c29.png)

### [2. Test 570](https://www.w3.org/Voice/2013/scxml-irp/570/test570.txml)
Immediately after generating done.state.id upon entering a final child of state, if the parent state is a child of a parallel element, and all of the parallel's other children are also in final states, the Processor MUST generate the event done.state.id where id is the id of the parallel element.

![test570](https://user-images.githubusercontent.com/18611095/28671579-e6e54b10-72e5-11e7-874b-33fb0a0dd5ca.png)
