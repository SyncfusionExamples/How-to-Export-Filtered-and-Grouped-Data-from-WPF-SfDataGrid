# How to Export Filtered and Grouped Data from WPF SfDataGrid

## Overview

This example demonstrates how to export filtered and grouped data from a Syncfusion WPF DataGrid (`SfDataGrid`) control. The sample project showcases best practices for exporting data in multiple formats while preserving the current view state including filters and grouping settings.

## Project Features

This WPF application provides a complete working example of:

- **Interactive Data Grid**: A fully functional `SfDataGrid` displaying order information with columns for Order ID, Customer ID, Customer Name, Country, and Ship City
- **Built-in Filtering**: Users can apply filters to the data grid to show only relevant records
- **Dynamic Grouping**: Support for grouping data by any column with a visual group drop area
- **Multi-Format Export Capabilities**:
  - **Excel Export**: Export filtered/grouped data to Excel (supporting Excel 97-2003, Excel 2010, and Excel 2013 formats)
  - **PDF Export**: Convert the current view to PDF format
  - **Print Preview**: View and print the grid with applied filters and groups
- **Automatic Format Selection**: Users can choose the desired Excel version during export
- **File Dialog Integration**: Built-in Save File Dialog for easy file selection and location
- **Post-Export Viewing**: Option to automatically open exported files in the default application

## Project Structure

```
Exporting_With_Filtering_Grouping/
├── App.xaml                          # WPF Application definition
├── App.xaml.cs                       # Application code-behind
├── MainWindow.xaml                   # Main UI with DataGrid and export buttons
├── MainWindow.xaml.cs                # Export logic and event handlers
├── Exporting_With_Filtering_Grouping.csproj  # Project file
├── Model/
│   └── OrderInfo.cs                  # Order data model with INotifyPropertyChanged
└── ViewModel/
    └── ViewModel.cs                  # ViewModel providing sample order data
```

## How It Works

### 1. **Data Model (OrderInfo.cs)**
- Represents order information with properties: OrderID, CustomerID, CustomerName, Country, ShipCity
- Implements `INotifyPropertyChanged` for data binding support
- Includes Display attributes for user-friendly column names

### 2. **ViewModel (ViewModel.cs)**
- Generates a collection of 10 sample orders
- Provides data binding through an `ObservableCollection<OrderInfo>`
- Contains realistic customer data from various countries

### 3. **User Interface (MainWindow.xaml)**
- Syncfusion SfDataGrid configured with:
  - `AllowGrouping="True"` - Enables grouping functionality
  - `AllowFiltering="True"` - Enables filtering capabilities
  - `ShowGroupDropArea="True"` - Displays area for drag-and-drop grouping
- Three action buttons for different export operations

### 4. **Export Logic (MainWindow.xaml.cs)**
- **OnExportToExcel()**: Exports the current view to Excel with selected format option
- **OnExportToPDF()**: Exports the current view to PDF format
- **OnPrinting()**: Shows print preview dialog for the grid

## Technology Stack

- **Framework**: .NET Framework
- **Language**: C#
- **UI Framework**: WPF (Windows Presentation Foundation)
- **Component**: Syncfusion DataGrid for WPF
- **Export Libraries**: Syncfusion XlsIO (Excel), Syncfusion PDF (PDF)

## Getting Started

### Prerequisites
- Visual Studio 2017 or higher
- .NET Framework 4.6.2 or higher
- Syncfusion WPF components (installed via NuGet)

### Setup Instructions

1. **Clone or Download** the repository
   ```bash
   git clone https://github.com/SyncfusionExamples/How-to-Export-Filtered-and-Grouped-Data-from-WPF-SfDataGrid.git
   ```

2. **Open in Visual Studio**
   - Open `Exporting_With_Filtering_Grouping.slnx` in Visual Studio

3. **Restore NuGet Packages**
   - Visual Studio will automatically restore Syncfusion dependencies
   - Or manually run: `nuget restore`

4. **Build and Run**
   - Build the solution (Ctrl+Shift+B)
   - Run the application (F5)

## Usage Guide

1. **Run the Application**
   - The window displays a data grid with sample order data
   
2. **Apply Filters** (Optional)
   - Click the filter icon in any column header
   - Select filter criteria to show only matching records

3. **Apply Grouping** (Optional)
   - Drag a column header to the "Drop groups here" area
   - Or right-click a column and select "Group by this column"

4. **Export Data**
   - Click **"Export to Excel"** to save filtered/grouped data as an Excel file
     - Choose format (Excel 97-2003, 2010, or 2013)
     - Select save location
     - Optionally view the file
   - Click **"Export to PDF"** to save as PDF
   - Click **"Print the Grid"** to preview and print

## Use Cases

- **Business Reports**: Export filtered sales data by region, date, or customer
- **Data Analysis**: Group data by country/city and export summarized results
- **Record Archival**: Archive specific subsets of data in Excel or PDF formats
- **Distributed Reports**: Generate and share filtered reports with stakeholders
- **Audit Trails**: Export specific records for compliance and auditing purposes

## Key Implementation Details

- The export respects the current view state (applied filters and grouping)
- Export is performed on `dataGrid.View` to include the current filtered/grouped view
- Excel exports support version selection (Excel 97 to 2013)
- PDF export creates a new PDF document from the grid data
- All exports use Syncfusion's export extensions for seamless integration

## Important Notes

- **Data Preservation**: Filters and grouping are preserved during export
- **Multiple Formats**: Choose between Excel (multiple versions) and PDF based on requirements
- **Sample Data**: The application includes 10 sample orders from various countries
- **Syncfusion License**: Requires valid Syncfusion license; evaluation mode is available for 30 days

## Requirements

- Visual Studio 2017 or higher
- .NET Framework 4.6.2 or higher
- Syncfusion WPF components (obtained via NuGet package manager)


## Support & Resources

- **Syncfusion WPF DataGrid Documentation**: [https://www.syncfusion.com/wpf-ui-controls/datagrid](https://www.syncfusion.com/wpf-ui-controls/datagrid)
- **API Reference**: Access detailed API documentation from the Syncfusion documentation portal
- **Support**: For issues or questions, contact Syncfusion support team

## Related Examples

Look for other Syncfusion WPF DataGrid examples in the SyncfusionExamples repository for features like:
- Data Binding and MVVM patterns
- Styling and Appearance customization
- Advanced Filtering and Sorting
- Editing and Validation
- Selection and Navigation
