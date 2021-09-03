# Avalonia.VisualStudio.Snippets
This is just a loose collection of some code snippets for Visual Studio. 

## Snippets currenty available: 

### avasp
Creates a simple `Avalonia.StyledProperty`

**Example**:
```c#
/// <summary>
/// Defines the <see cref="Test"/> property.
/// </summary>
public static readonly StyledProperty<string> TestProperty =
    AvaloniaProperty.Register<MyControl, string>(nameof(Test), "This is easy :-)");

/// <summary>
/// This is just a sample property
/// </summary>
public string Test
{
    get { return GetValue(TestProperty); }
    set { SetValue(TestProperty, value); }
}
```