# Goldsmith Developer's Documentation

1/22

- 'Buttons, Links, and Actions' are located under Setup->Customize->Assets
- The text field 'Notes' for Client Report is the `Client_Report_Status_2__c` custom object. It's currently a TextArea(255) datatype, but switching it to TextArea(long) requires all references to `Client_Report_Status_2__c` in the rest of the CMS to be temporarily removed or commented out. Salesforce will not validate the change to TextArea(long) if there exist any references to objects of the old datatype.

