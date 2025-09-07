# binding-selected-items-treeview-xamarin
This repository demonstrates how to bind and manage selected items in the Xamarin.Forms SfTreeView control. It provides a sample implementation that shows how to synchronize the selection state between the TreeView and the ViewModel, enabling multiple selection and real-time updates through data binding.

## Sample

### XAML
```xaml
<ContentPage.Content>
    <syncfusion:SfTreeView x:Name="treeView"
                         ItemHeight="40"
                         Indentation="40"
                         ExpanderWidth="40"
                         SelectionMode="Multiple"
                         ChildPropertyName="States" 
                         SelectionBackgroundColor="#E4E4E4"
                         ItemsSource="{Binding CountriesInfo}"
                         SelectedItems="{Binding SelectedCountries}"
                         AutoExpandMode="RootNodesExpanded">
        <syncfusion:SfTreeView.ItemTemplate>
            <DataTemplate>
                <Grid Padding="5,0,0,0">
                    <Label Text="{Binding Name}" 
                               FontSize="Medium"
                               VerticalTextAlignment="Center"/>
                </Grid>
            </DataTemplate>
        </syncfusion:SfTreeView.ItemTemplate>
    </syncfusion:SfTreeView>
</ContentPage.Content>
```

### ViewModel
```csharp
public class CountriesViewModel
{
    public CountriesViewModel()
    {
        GenerateCountriesInfo();
    }

    public ObservableCollection<object> SelectedCountries { get; set; }

    private void GenerateCountriesInfo()
    {
        SelectedCountries = new ObservableCollection<object>();
        SelectedCountries.Add(_NSW);
        SelectedCountries.Add(victoria);
    }
} 
```

## Requirements to run the demo

To run the demo, refer to [System Requirements for Xamarin](https://help.syncfusion.com/xamarin/system-requirements)

## Troubleshooting
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.
