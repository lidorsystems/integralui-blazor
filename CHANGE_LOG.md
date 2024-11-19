v24.3
- New Components:
- <strong>Grid</strong> - Displays tabular data sets with advanced Editing, Grouping, Pagination, Filtering, Sorting and more
- <strong>Pager</strong> - Allows you to divide the content in multiple views
- <strong>Panel</strong> - Generic container with option for content alignment
- <strong>Validator</strong> - Displays a notification message when data is invalid
- Optimized layout update for List, ListBox and TreeView components
- Editor components now have IsValid property that when true applies a red outline
- ListView component allows column definitions in Razor and also optionally with data binding
- In List component when MaxVisibleItems property is greater than 0, the max scroll size is now correctly adjusted
- Select component now includes MouseWheelSpeed property that changes the scrolling speed of dropdown list
- Animation of dropdown window in Select is now correctly applied from AllowAnimation property
- A new class is added for tooltip that enwraps the displayed content
- New CSS properties for TreeView to enable text trimming
- Fixed the issue that caused incorrect values to appear in custom item template when scrolling
- Fixed the update issue caused by setting dynamic key for menu items when Id is not present
- Fixed the firing of MenuClick event to occur after Checked property changes
- Other minor bug fixes

v24.2
- New Components:
- <strong>Calendar</strong> - Enables the user to select a date using a visual monthly calendar display
- <strong>DatePicker</strong> - Allows the user to select a date by using a drop-down calendar
- <strong>List</strong> - Displays a simple list of items
- <strong>ProgressBar</strong> - Visualize the progression of an operation
- <strong>Rating</strong> - Visualizes ratings
- <strong>Slider</strong> - Allows changes to a numeric value within a range of defined minimum and maximum values
- Optimized layout update for List, ListBox and TreeView components
- ListView component allows column definitions in Razor and also optionally with data binding
- Option to create deep copies of items in List, ListBox, ListView and TreeView
- Card component now includes an event fired when Flipped property changes
- Fixed the issue with update of CheckBox value in TreeView for parent-child items
- DragDrop between two components now works correctly when one component is empty
- Selection is now cleared on drag and drop between components
- Fixed the drag and drop issue that caused item to appear as duplicate in the tree hierarchy, when moved from one parent to another
- With AllowDrop set to false in TreeView, when item with children is dragged outside of component space is now collapsed
- Pressing ESCAPE to cancel drag and drop closes the drag window in source and target components
- Drag Drop Icon change to NO DROP when drag and drop is cancelled is now fixed
- Fixed the issues that caused drag and drop to slow down when items in TreeView have check boxes with three state values
- Fixed the issues with update of check box value in parent-child items during drag and drop in TreeView
- Fixed the issue that caused duplicates during multi drag and drop in TreeView when parent/child items are dragged
- Other minor bug fixes

v24.1
- Initial Release
