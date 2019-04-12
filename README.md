# Lightning-Modal
Component for Modal

## Usage
1. add the following code to your lightning component:

* &lt;!-- add the component to your component body --&gt;
```
<c:CmpModal aura:id="myModal" title="My fancy Modal" allowClose="true/false">

	<!-- place your action buttons in the footer of the modal -->
	<aura:set attribute="footer">
	</aura:set>

	<!--- body of your modal here -->
</c:CmpModal>

Example:

<c:CmpModal aura:id="myModal" title="Select Email Template" allowClose="true">
		
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

```



2. add the following code to your lightning javascript:

* to display the modal, do this: 
```javascript
component.find("myModal").openModal();
```

* to close the modal, do this:
```javascript
component.find("myModal").closeModal();

Example:
For the example component we created above, we ccould use this javascript in out controller:


    save: function (component, event, helper)
    {
    	// do your save stuff
    	// Then, close the modal
        component.find('myModal').closeModal();
    },

    cancel: function (component, event, helper)
    {
        component.find('myModal').closeModal();
    },
```

## Install Steps:
* Use the botton below to deploy the code to your org:

<a href="https://githubsfdeploy.herokuapp.com?owner=veenasundara&repo=Lightning-Modal">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/src/main/webapp/resources/img/deploy.png">
</a>
