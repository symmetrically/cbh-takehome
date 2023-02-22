# Ticket Breakdown
We are a staffing company whose primary purpose is to book Agents at Shifts posted by Facilities on our platform. We're working on a new feature which will generate reports for our client Facilities containing info on how many hours each Agent worked in a given quarter by summing up every Shift they worked. Currently, this is how the process works:

- Data is saved in the database in the Facilities, Agents, and Shifts tables
- A function `getShiftsByFacility` is called with the Facility's id, returning all Shifts worked that quarter, including some metadata about the Agent assigned to each
- A function `generateReport` is then called with the list of Shifts. It converts them into a PDF which can be submitted by the Facility for compliance.

## You've been asked to work on a ticket. It reads:

**Currently, the id of each Agent on the reports we generate is their internal database id. We'd like to add the ability for Facilities to save their own custom ids for each Agent they work with and use that id when generating reports for them.**


Based on the information given, break this ticket down into 2-5 individual tickets to perform. Provide as much detail for each ticket as you can, including acceptance criteria, time/effort estimates, and implementation details. Feel free to make informed guesses about any unknown details - you can't guess "wrong".


You will be graded on the level of detail in each ticket, the clarity of the execution plan within and between tickets, and the intelligibility of your language. You don't need to be a native English speaker, but please proof-read your work.

## Your Breakdown Here


# Ticket 1: Add Custom ID field to Agents table
### Effort Estimate: 4-6 hours

```bash
Acceptance Criteria:

A new field called "custom_id" is added to the Agents table in the database
Custom ID field can be updated by the Facility
Custom ID is displayed on the Shifts list in the Facilitys dashboard
Custom ID is used on generated reports instead of the internal database ID
Implementation Details:

Add a new column to the Agents table in the database to store custom ID
Create an API endpoint to update the custom ID field
Update the Shifts list to display the custom ID instead of internal database ID
Update the generateReport function to use the custom ID when generating reports
```

# Ticket 2: Add Custom ID to Shifts metadata
### Effort Estimate: 3-4 hours

```bash
Acceptance Criteria:

Custom ID is saved as metadata for each Shift assigned to an Agent
Custom ID is displayed on the Shift details page in the Facilitys dashboard
Custom ID is used on generated reports instead of the internal database ID

Implementation Details:
Update the Shifts table to include the custom ID field
Modify the getShiftsByFacility function to retrieve the custom ID for each Shift
Update the Shift details page in the Facilitys dashboard to display the custom ID
Update the generateReport function to use the custom ID when generating reports
```


# Ticket 3: Create form for Facility to update Custom ID
### Effort Estimate: 3-4 hours

```bash
Acceptance Criteria:

A form is created in the Facilitys dashboard to allow them to update the custom ID for an Agent
The form is user-friendly and requires validation to ensure unique custom ID per Agent
Updating the custom ID is reflected in the Shifts list and Shift details page
Implementation Details:

Create a new form in the Facilitys dashboard to update the custom ID for an Agent
Add validation to ensure unique custom ID per Agent
Update the Shifts list and Shift details page to reflect the new custom ID
```

# Ticket 4: Modify report generation to include Custom ID
### Effort Estimate: 2-3 hours

```bash
Acceptance Criteria:

Custom ID is included in the generated report for each Agent
Custom ID is displayed in a prominent location and is easily readable
The report generation process still works as before and does not cause any performance issues
Implementation Details:

Update the generateReport function to include the custom ID for each Agent in the report
Position the custom ID in a prominent location in the report
Test the report generation process to ensure it still works as before and does not cause any performance issues
```