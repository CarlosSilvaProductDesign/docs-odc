---
tags: runtime-mobileandreactiveweb;  
summary: Use the Center Content pattern to align the content to the center of its container.
---

# Center Content

You can use the Center Content UI Pattern to vertically align content to the center of its container.

![](<images/centercontent-1.png>)

**How to use the Center Content UI Pattern**

1. In Service Studio, in the Toolbox, search for `Center Content`.

    The Center Content widget is displayed.

    ![](<images/centercontent-2-ss.png>)

    If the UI widget does not display, it may be because you used a ready-made app, which deletes unused widgets from the module. To make additional widgets available in your app:

    a. Go to **Module > Manage dependencies**.

    b. Search for and select the relevant Producer, for example OutSystemsUI. Ensure Show All is selected. 

    c. On the Public elements for the selected Producer displayed on the right, ensure Show All is selected.
    
    d. Search for and select the element you want to add, and click **Apply**. 
    
    e. In Service Studio, in the Toolbox, search for the widget again.

1. From the Toolbox, drag the Center Content widget into the Main Content area of your application's screen.

    ![](<images/centercontent-3-ss.png>)

    By default, the Center Content widget contains Top, Center, and Bottom placeholders.

1. Add the relevant content to each of the placeholders. In this example we add some images and text.

    ![](<images/centercontent-4-ss.png>)

After following these steps and publishing the module, you can test the pattern in your app.

## Properties

| Property | Description |
|---|---|
| ExtendedClass (Text): Optional | <p>Adds custom style classes to the Pattern. You define your [custom style classes](../../../look-feel/css.md) in your application using CSS.</p> <p>Examples <ul><li>_Blank_ - No custom styles are added (default value).</li><li>_"myclass"_ - Adds the _myclass_ style to the UI styles being applied.</li><li>_"myclass1 myclass2"_ - Adds the _myclass1_ and _myclass2_ styles to the UI styles being applied.</li></ul></p>You can also use the classes available on the OutSystems UI. For more information, see the [OutSystems UI Live Style Guide](https://outsystemsui.outsystems.com/StyleGuidePreview/Styles). |
