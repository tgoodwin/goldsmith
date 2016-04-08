# Goldsmith Developer's Documentation

###1/22

- 'Buttons, Links, and Actions' are located under Setup->Customize->Assets
- The text field 'Notes' for Client Report is the `Client_Report_Status_2__c` custom object. It's currently a TextArea(255) datatype, but switching it to TextArea(long) requires all references to `Client_Report_Status_2__c` in the rest of the CMS to be temporarily removed or commented out. Salesforce will not validate the change to TextArea(long) if there exist any references to objects of the old datatype.
-- references:
  clientReportController - 5 references
  exportClientReport
  MasterView

###4/8

Note: Company and Account are essentially the same

Creating a Related List of [Object 1] in [Object 2]
e.g. Create a related list of campaign member objects of a certain company on that company's page

1) Create a lookup(Account) field in the object that you want to populate the related list
- This will actually create a 'relationship' between the two objects
- Otherwise, the 'Company' field of the campaign member object is actually just a text field

2) Add the related list to the company page

3) Then using the Process Builder create a Process on the Campaign Member object that inserts the Capmaign Member: Contact.AccountId into your custom Campaign Member: Lookup(Account) field.
- This seems complicated, but it's actually pretty intuitive

After these steps, whenever a contact is added to a campaign and a campaign member object is created, the process will lookup the company ID, creating a relationship between the campaign member object and the company object.
