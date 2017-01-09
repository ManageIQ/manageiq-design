# Dialogs

- "Dialogs" is a secondary item under the "Designer" category
- This area is for the Service Designer and is not visible to other users
- This area is provided so the Designer can create and edit service dialogs

## Dialog Editor

### Blank Dialog Editor

![Blank dialog editor](img/DialogEditor-01.png)
- When the user creates a new dialog, they are brought to this screen with a single tab and section already populated.

#### Implementation Details
- The Dialog Editor should follow the same conventions as the blueprint editor when generating names for new dialogs and dialog elements. (e.g. Untitled Dialog")

### Placing a dialog element
![Placing an element](img/DialogEditor-02.png)
- Hovering over an element in the toolbar or on the canvas should show a grab handle and outline of the element

![Element being placed](img/DialogEditor-03.png)
- The user may click and drag the element to a specific place, or click on it once which will place it at the end of the lowest section on the current tab

### Editing an element
![Element with revealed edit button](img/DialogEditor-04.png)
- Elements can be duplicated and deleted by selecting them and clicking the duplicate and delete buttons in the toolbar.
- Hovering over a placed element will show the edit icon

![Element editor modal](img/DialogEditor-05.png)
- Clicking the edit icon should bring up the element editor modal

#### Implementation Details
  - The title of the modal should be "Edit [type of element]"

### Stretch Featues (Optional)
![Editor with properties panel](img/DialogEditor-06.png)
- Space and technology permitting, the element editor modal should be replaced with an element properties panel that enables the user to edit the selected element in real time.
- Undo and Redo features would be required for this to be effective
- Checking the "Preview Dialog" option would hide the toolbox and properties panel and display the dialog as it would appear when it is being used.

## Customer Feedback

### Customer Feedback Received
  - Overview of customer feedback received

### Necessary Customer Feedback
  - Questions to follow up with customers
