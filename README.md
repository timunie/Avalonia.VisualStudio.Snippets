# Avalonia.VisualStudio.Snippets
This is just a loose collection of some code snippets for Visual Studio. 

## Snippets currenty available: 

### avasp
Creates a simple `Avalonia.StyledProperty` [read more](https://docs.avaloniaui.net/docs/authoring-controls/defining-properties#registering-styled-properties)

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

-----------

### avaap
Creates a simple `Avalonia.AttachedProperty` [read more](https://docs.avaloniaui.net/docs/authoring-controls/defining-properties#attached-properties)

**Example**:
```c#
/// <summary>
/// Defines an AttachedProperty
/// </summary>
public static readonly AttachedProperty<string> TestAttachedProperty = AvaloniaProperty.RegisterAttached<Owner, Host, string>(
    "TestAttached", "My attached property");


/// <summary>
/// Accessor for Attached property <see cref="TestAttachedProperty"/>.
/// </summary>
public static void SetTestAttached(AvaloniaObject element, string value)
{
    element.SetValue(TestAttachedProperty, value);
}

/// <summary>
/// Accessor for Attached property <see cref="TestAttachedProperty"/>.
/// </summary>
public static string GetTestAttached(AvaloniaObject element)
{
    return element.GetValue(TestAttachedProperty);
}
```

-----------

### avarop
Creates a simple `Avalonia.ReadonlyProperty` [read more](https://docs.avaloniaui.net/docs/authoring-controls/defining-properties#readonly-properties)

**Example**:
```c#
/// <summary>
/// Defines the <see cref="TestReadonly"/> property.
/// </summary>
public static readonly DirectProperty<Control, string> TestReadonlyProperty =
    AvaloniaProperty.RegisterDirect<Control, string>(nameof(TestReadonly), o => o.TestReadonly);

/// <summary>
/// A readonly property
/// </summary>
public string TestReadonly
{
    get { return GetValue(TestReadonlyProperty); }
    private set { SetValue(TestReadonlyProperty, value); }
}
```

----------

### propr
Creates a simple `Avalonia.AttachedProperty` [read more](https://www.reactiveui.net/docs/handbook/view-models/#read-write-properties)

**Example**:
```c#
private object _MyProperty;

/// <summary>
/// Gets or sets my property
/// </summary>
public object MyProperty
{
    get { return _MyProperty; }
    set { this.RaiseAndSetIfChanged(ref _MyProperty, value); }
}
```

----------

### rxval
Snippet to implement a basic validation rule [read more](https://www.reactiveui.net/docs/handbook/user-input-validation/)

**Example**:
```c#
this.ValidationRule(
    validator => validator.ID,
    _ID => _ID.HasValue,
    "The ID must have a value");
```