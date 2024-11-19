# IntegralUI for Blazor, v24.3

IntegralUI for Blazor is UI library of advanced, customizable and high performance components for Blazor .NET. 

![IntegralUI for Blazor 24.3](https://www.lidorsystems.com/products/integralui/blazor/integralui-blazor-243000.png)

Here is a brief overview of what is included:

## Components

[Button](https://www.lidorsystems.com/products/integralui/blazor/samples/button/overview) - Represents a button

[ButtonGroup](https://www.lidorsystems.com/products/integralui/blazor/samples/buttongroup/overview) - Manages actions of multiple buttons arranged in group

[Calendar](https://www.lidorsystems.com/products/integralui/blazor/samples/calendar/overview) - Enables the user to select a date using a visual monthly calendar display

[Card](https://www.lidorsystems.com/products/integralui/blazor/samples/card/overview) - A flip card with two sides

[CheckBox](https://www.lidorsystems.com/products/integralui/blazor/samples/checkbox/overview) - Represents a check box

[ContextMenu](https://www.lidorsystems.com/products/integralui/blazor/samples/contextmenu/overview) - Represents a multi-level shortcut menu

[DatePicker](https://www.lidorsystems.com/products/integralui/blazor/samples/datepicker/overview) - Allows the user to select a date by using a drop-down calendar

[DropDown]() - Shows other components in a dropdown window

[Grid](https://www.lidorsystems.com/products/integralui/blazor/samples/grid/overview) - Displays tabular data sets with advanced Editing, Grouping, Pagination, Filtering, Sorting and more

[List](https://www.lidorsystems.com/products/integralui/blazor/samples/list/overview) - Displays a simple list of items

[ListBox](https://www.lidorsystems.com/products/integralui/blazor/samples/listbox/overview) - Displays a collection of items with content in custom layouts

[ListView](https://www.lidorsystems.com/products/integralui/blazor/samples/listview/overview) - Displays a collection of items using several different views

[Menu](https://www.lidorsystems.com/products/integralui/blazor/samples/menu/overview) - Allows you to create static or dynamic menus

[Pager](https://www.lidorsystems.com/products/integralui/blazor/samples/pager/overview) - Allows you to divide the content in multiple views

[Panel](https://www.lidorsystems.com/products/integralui/blazor/samples/panel/overview) - Generic container with option for content alignment

[PopOver](https://www.lidorsystems.com/products/integralui/blazor/samples/popover/overview) - Displays custom HTML content over specified element

[ProgressBar](https://www.lidorsystems.com/products/integralui/blazor/samples/progressbar/overview) - Visualize the progression of an operation

[RadioButton](https://www.lidorsystems.com/products/integralui/blazor/samples/radiobutton/overview) - Represents a radio button

[Rating](https://www.lidorsystems.com/products/integralui/blazor/samples/rating/overview) - Visualizes ratings

[Select](https://www.lidorsystems.com/products/integralui/blazor/samples/select/overview) - Allows you to select an item from a dropdown list

[Slider](https://www.lidorsystems.com/products/integralui/blazor/samples/slider/overview) - Allows changes to a numeric value within a range of defined minimum and maximum values

[Tooltip](https://www.lidorsystems.com/products/integralui/blazor/samples/tooltip/overview) - Adds a tooltip to an element

[TreeList](https://www.lidorsystems.com/products/integralui/blazor/samples/treelist/overview) - Allows you to navigate through tree hierarchy showing only one list at a time

[TreeView](https://www.lidorsystems.com/products/integralui/blazor/samples/treeview/overview) - Displays hierarchical data structures

[Validator]() - Displays a notification message when data is invalid


## Dependencies

IntegralUI for Blazor is built with .NET 8.0 framework.


## DEMO

[Online QuickStart App](https://www.lidorsystems.com/products/integralui/blazor/samples/) - An online demo of each component included


## Installation

Once you complete with installtion of the latest version, you can use all components available in IntegralUI library. There are few namespaces that you can import:

IntegralUI.Components
IntegralUI.Data
IntegralUI.Events
IntegralUI.Interfaces
IntegralUI.Services
IntegralUI.Styling

All components are located under IntegralUI.Components namespace.


### How to Use IntegralUI components in Blazor Apps

At first, you need to install the IntegralUI for Blazor library on your side and add a reference to a component you want to use.

In case of IntegralUI Grid component, you need to do the following:

1. Open a Blazor page in your project
2. Add code line that will import the IntegralUI components
3. Place the Grid component using the IntegralUIGrid tag
4. Specify the generic TModel type that you will use as a data model
5. Set the DataSource property to connect the Grid to your data source
6. Define the columns in razor using the IntegralUIGridColumn tag where you can specify different properties and templates regarding Grid columns
7. (optional) Define the template that will be used to create the content for rows using the RowTemplate
8. (optional) Add custom HTML elements or other Blazor components inside the template
9. (optional) Add other features like sorting, filtering etc. require corresponding property or event to be set
10. (optional) Set up dynamic styles within Styles tag for specific target: Column, Row, Cell etc
11. (optional) Create a reference to the component using the @ref attribute, to call public methods

For example:

```
@page "/"

<IntegralUIGrid @ref=gridRef Id="grid-overview" TModel="CustomData" 
    DataSource="@gridRows"
    Size="@gridSize"
    ColumnClick="@gridColumnClick">
    <Columns>
        <IntegralUIGridColumn Field="Country" MenuItems="@gridMenuItems" MenuPositionAdjustment="@gridMenuPositionAdjustment" Width="350"></IntegralUIGridColumn>
        <IntegralUIGridColumn Field="Population" FormatSpecifier="N0" ContentAlignment="IntegralUIHorizontalAlignment.Right" Width="180"></IntegralUIGridColumn>
        <IntegralUIGridColumn Field="PercentWorld" HeaderText="% of World" FormatSpecifier="P2" ContentAlignment="IntegralUIHorizontalAlignment.Right" Width="150"></IntegralUIGridColumn>
        <IntegralUIGridColumn Field="Date" FormatSpecifier="dd MMM yyyy" ContentAlignment="IntegralUIHorizontalAlignment.Center" Width="180"></IntegralUIGridColumn>
        <IntegralUIGridColumn Field="Land" HeaderText="Land in km2" FormatSpecifier="N0" ContentAlignment="IntegralUIHorizontalAlignment.Right" Width="150"></IntegralUIGridColumn>
        <IntegralUIGridColumn Field="Capital" ContentAlignment="IntegralUIHorizontalAlignment.Center" Width="200"></IntegralUIGridColumn>
    </Columns>
    <RowTemplate>
        @switch (context.Cell?.Field)
        {
            case "Country":
                <div>
                    <span class="grid-sorting-flags @(getCountryIcon((string?)context.Row?.Country))"></span>
                    <span class="grid-sorting-country">@context.Row?.Country</span>
                </div>
                break;

            default:
                <div class="grid-sorting-cell-label">@context.DisplayValue</div>
                break;
        }
    </RowTemplate>
    <Styles>
        <IntegralUIStyle TargetType="IntegralUITargetType.Row" ConditionIndex="@evenOddStyle" Background="#f9f9f9"></IntegralUIStyle>
    </Styles>
</IntegralUIGrid>

@code {
    // Get a reference to the IntegralUI Grid component to call public methods
    private IntegralUIGrid<CustomData>? gridRef;

    // Data
    private class CustomData
    {
        public string? Country { get; set; }
        public int Population { get; set; } = 0;
        public double PercentWorld { get; set; } = 0;
        public DateTime Date { get; set; } = DateTime.Today;
        public int Land { get; set; } = 0;
        public string? Capital { get; set; }

        // State Properties
        public bool Selected { get; set; } = false;
    }

    // Define the component size
    public IntegralUISize ctrlSize = new() { Width = 350, Height = 300 };

    // Add data to the Grid component
    private List<CustomData> gridRows = new()
    {
        new CustomData()
        {
            Country = "Japan",
            Population = 123780000,
            PercentWorld = 0.015,
            Date = new DateTime(2024, 9, 1),
            Land = 364555,
            Capital = "Tokyo"
        },

        // . . .
    };

    // Specify the size of the Grid component
    public IntegralUISize gridSize = new() { Height = 400 };

    //
    // Handle the ColumnClick event to sort the Grid data whenever column is clicked
    //

    private void gridColumnClick(IntegralUIDataColumn column)
    {
        if (column is not null)
        {
            // Only change the order if same column is clicked
            if (prevSortColumn is not null && !EqualityComparer<IntegralUIDataColumn>.Default.Equals(column, prevSortColumn))
            {
                prevSortColumn.Selected = false;
                column.Sorting = prevSortColumn.Sorting;
            }
            else
            {
                switch (column.Sorting)
                {
                    case IntegralUISortOrder.Ascending:
                        column.Sorting = IntegralUISortOrder.Descending;
                        break;

                    case IntegralUISortOrder.Descending:
                        column.Sorting = IntegralUISortOrder.None;
                        break;

                    default:
                        column.Sorting = IntegralUISortOrder.Ascending;
                        break;
                }
            }

            prevSortColumn = column;

            // Call the Sort method
            gridRef?.Sort(column, column.Sorting ?? IntegralUISortOrder.Ascending);
        }
    }

    //
    // Change the Grid appearance using dynamic styles by providing a condition by which in this case rows are displayed in alternate colors 
    //

    private bool evenOddStyle(object? obj, int index)
    {
        return index % 2 == 1;
    }

}
```


## QuickStart App

There is a demo application with source code that contains samples for each component included in the IntegralUI for Blazor product package. It can help you to get started quickly with learning about the components and write tests immediatelly. 

The Quick Start project is available as part of IntegralUI QuickStart application project included with product package: [IntegralUI for Blazor - Download](https://www.lidorsystems.com/downloads/integralui-blazor-reg.aspx)</a>.


## License Information

You may use this product to develop Internet and Intranet web sites, web applications and other products. To unlock the product and remove Trial window from showing, you will need a license key.

This project has been released under the IntegralUI for Blazor License, and may not be used except in compliance with the License.
A copy of the License should have been embedded within this project package or it can be found here: [License Agreement](https://www.lidorsystems.com/products/integralui/blazor/license-agreement.aspx).

This SOFTWARE is provided "AS IS", WITHOUT WARRANTY OF ANY KIND, either express or implied. See the License for the specific language governing rights and limitations under the License.