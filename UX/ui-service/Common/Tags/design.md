# Tags - Common Component
* Tags are used in multiple areas throughout the UI.
* Tags are made up of two parts, a category and value. Some categories allow for more than one value to be associated.  
* Tags can be applied to a single item or multiple items at one time depending on the use case.
* In all cases, the Tag selection dropdowns and the tag labels should be visually consistent.
* As tags are added, they should be placed at the bottom of the list. Once saved, the tags should be reordered into alphabetic order so upon returning to the tags area, users can easily scan the list.

## Simple Tags
  * ![Image of a Simple Tag.](img/SimpleTags-01.png)  

1. **Selection:**
  * A combobox should be used for the tag selection so users can rely on the dropdown or they can type to filter the list of options.
  * Once a category has been chosen from the first dropdown, the second dropdown should be enabled.

2. **Labels:**
  * Once the user selects an option from the second dropdown, the tag label should be added below the selection boxes.
  * The entire label should have a dark boarder with the category left aligned.
  * The value should be displayed to the right of the category, with a lighter boarder to distinguish it.
  * Each value should have an x icon right aligned to allow for removing it.

  * ![Image of Label with a Single Value.](img/SingleValue.png)  
  * If the Tag only has one value associated with the category, clicking the x on that value will remove the entire tag.  

3. **Multi-Value Tags:**   
  * For cases where the category allows for more than one value to be associated, the second dropdown will indicate the values that have already been applied using the multiple select dropdown widget.
  * Implementation Details: Use the [Bootstrap Multiple Select](http://www.patternfly.org/pattern-library/widgets/#bootstrap-select) for the values dropdown.
  * Values can be removed by either deselecting items in the dropdown or by clicking the x next to the tag.
  * Additional values are added to the right of the initial value and each has an x icon for removal.  

  * ![Image of Label with Multiple Values.](img/MultiValue.png)  

4. **Empty State:**
  * When there are no tags associated with an item, the empty state should show the following text: "There are no tags associated" in the area where tags would be added.

  * ![Image of a Simple Tag.](img/SimpleTags-Empty.png)  

## Tagging Multiple Items

* ![Image of Advanced Tags.](img/AdvancedTags-01.png)  

* When tagging multiple items at once, there should be an additional section showing the items that will be affected by the changes.
* In the example shown, Services are being tagged, so the service icons would appear under the "Affected Services" label below all of the listed tags.
* In cases where a category has too many values associated with it, the darker blue background may wrap to the next line to accommodate for additional values.

* ![Image of Advanced Tags.](img/AdvancedTags-02.png)  
