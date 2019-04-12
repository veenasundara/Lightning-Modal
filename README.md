# Lightning-Modal
Component for Modal

## Usage
1. To add a modal, place this code in your lightning component. The modal will be closed by default and needs to be opened using javascript.

```
<c:CmpModal aura:id="myModal" title="My fancy Modal" allowClose="true/false">

	<!-- place your action buttons in the footer of the modal -->
	<aura:set attribute="footer">
	</aura:set>

	<!--- body of your modal here -->
</c:CmpModal>

```

2. To open the modal, use this in your lightning javascript:

```javascript
component.find("myModal").openModal();
```

3. To close the modal, use this in your lightning javascript:

```javascript
component.find("myModal").closeModal();
```

3. Example:

* A component with a button that will open the modal when clicked
```
<aura:component>

    <lightning:button label="My Action" onclick="{!c.open}"/>


    <!-- your modal which will stay closed till you open in -->
    <c:CmpModal aura:id="myModal" title="My Action" allowClose="true">
		
	<!-- buttons for modal footer -->
        <aura:set attribute="footer">
            <div class="slds-clearfix">
                <div class="slds-float--right">
                    <lightning:button label="Cancel" onclick="{!c.cancel}"/>
                    <lightning:button label="Save" variant="brand" onclick="{!c.save}"/>
                </div>
            </div>
        </aura:set>

    	<!-- modal content -->
        <lightning:input name="input1" label="Input1"/>

        <lightning:input name="input2" label="Input2"/>

    </c:CmpModal>	
</aura:component>
```
* Javascript controller code
```
({
	open : function(component, event, helper) {
		component.find("myModal").openModal();
	}

    save: function (component, event, helper)
    {
    	// do your save stuff


    	// close the modal
        component.find('myModal').closeModal();
    },

    cancel: function (component, event, helper)
    {
    	// close the modal
        component.find('myModal').closeModal();
    },
})   
```

## Install Steps:
* Use the botton below to deploy the code to your org:

<a href="https://githubsfdeploy.herokuapp.com?owner=veenasundara&repo=Lightning-Modal">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/src/main/webapp/resources/img/deploy.png">
</a>
