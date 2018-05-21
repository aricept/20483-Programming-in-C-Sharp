# Module 3:  Developing the Code for a Graphical Application

# Lesson 1:  Implementing Structs and Enums

### Demonstration: Creating and Using a Struct

#### Preparation Steps

1. Ensure that you have cloned the 20483C directory from GitHub. It contains the code segments for this course's labs and demos. https://github.com/MicrosoftLearning/20483-Programming-in-C-Sharp/tree/master/Allfiles


#### Demonstration Steps

1.  Open **Visual Studio 2017**.
2.  In Visual Studio, on the **File** menu, point to **New**, and then click
    **Project**.
3.  In the **New Project** dialog box, in the **Installed** list, click **Visual
    C\#**, and then in the **Project Type** list, click **Console App(.NET Framework)**.
4.  In the **Name** box, type **UsingStructs**
5.  In the **Location** box, set the location to **[Repository Root]\\Allfiles\\Mod03\\Democode**, and
    then click **OK**.
6.  In the **UsingStructs** namespace, add the following code:
    ```cs
    struct Coffee
    {
       public string Name { get; set; }
       public string Bean { get; set; }
       public string CountryOfOrigin { get; set; }
       public int Strength { get; set; } 
    }
    ```
7.	In the **Program** class, in the **Main** method, add the following code:
    ```cs
    Coffee coffee1 = new Coffee();
    coffee1.Name = "Fourth Coffee Quencher";
    coffee1.CountryOfOrigin = "Indonesia";
    coffee1.Strength = 3;

    Console.WriteLine("Name: {0}", coffee1.Name);
    Console.WriteLine("Country of Origin: {0}",coffee1.CountryOfOrigin);
    Console.WriteLine("Strength: {0}", coffee1.Strength);
    ```
8.  Notice that you are able to use the **Coffee** struct in the same way that
    you would use a standard .NET Framework type.
9.  On the **Build** menu, click **Build Solution**.
10.  On the **Debug** menu, click **Start Without Debugging**.
11.  Notice that the **Coffee** struct works just like a standard .NET Framework
    type at runtime.
12.  Press Enter to close the console window.
13.  Close Visual Studio.



# Lesson 3:  Handling Events

#### Preparation Steps

1. Ensure that you have cloned the 20483C directory from GitHub. It contains the code segments for this course's labs and demos. https://github.com/MicrosoftLearning/20483-Programming-in-C-Sharp/tree/master/Allfiles

### Demonstration: Working with Events in XAML

1.  Open **Visual Studio 2017**.
2.  In Visual Studio, on the **File** menu, point to **Open**, and then click
    **Project/Solution**.
3.  In the **Open Project** dialog box, browse to the
    **[Repository Root]\\Mod03\\Democode\\Starter** folder, click **EventsAndXAML.sln**, and
    then click **Open**.
4.  In Solution Explorer, expand **EventsAndXAML**, and then double-click
    **MainWindow.xaml**.
5.  Notice that the window includes a button named **btnGetTime** and a label
    named **lblShowTime**.
6. In the **Design** window, click the button to select it.
7. In the **Properties** window, ensure that **btnGetTime** is selected, and
    then click **Events**. The **Events** button is marked with a lightning
    button.
8. Notice that the **Properties** window now displays a list of the events to
    which you can subscribe.
9. In the **Properties** window, double-click inside the **Click** text box.
10. Notice that Visual Studio creates an event handler method for you and
    switches to the code behind page.
11. In the **btnGetTime_Click** method, add the following code:
    ```cs
    lblShowTime.Content = DateTime.Now.ToLongTimeString();
    ```
12. In Solution Explorer, expand **MainWindow.xaml**, expand
    **MainWindow.xaml.cs**, and then double-click **MainWindow**.
13. Switch back to the **MainWindow.xaml** window.
14. In the **Button** element, note that the designer has added the following
    attribute:
    ```cs
    Click="btnGetTime_Click"
    ```
This attribute subscribes the **btnGetTime_Click** method to the **Click**
event.
15. In Solution Explorer, expand **obj**, expand **Debug**, and then
    double-click **MainWindow.g.i.cs**.
16. Near the bottom of the file, notice that Visual Studio has added the
    following line of code:
    ```cs
    this.btnGetTime.Click += new System.Windows.RoutedEventHandler(this.btnGetTime_Click);
    ```
17. This demonstrates that Visual Studio parses the XAML to create the code that
subscribes your event handler method to the **Click** event of the button.
18.  On the **File** menu, click **Close**.
19.  On the **Debug** menu, click **Start Without Debugging**.
20.  Click **What's the time?** button several times.
21.  Notice that the label displays the current time.
22.  Close the application, close the solution, and then close Visual Studio.


### Demonstration: Writing Code for the Grades Prototype Application Lab

1.  Open the **GradesPrototype.sln** solution from the
    **[Repository Root]\\Mod03\\Labfiles\\Solution\\Exercise 3** folder.
2.  Run the application and log on as **vallee** with a password of
    **password**.
3.  Point out the **Welcome** message and class name to students. Explain that
    each of the names in the display is a student in Esther Valle’s class.
4.  Click **Kevin Liu** and explain to students that this page displays Kevin’s
    grades.
5.  Click **Back** and then click **Log off**.
6.  Log on as **liuk** with a password of **password**.
7.  Explain that because Kevin is a student, he can only see his own grades.
8.  Click **Log off**.
9.  Log on as **parkerd** with a password of **password**. Note the failure
    message.
10. Click **OK**, then and close the application.
11. In Visual Studio, in the **Data** folder, open **Grade.cs** and explain to
    students that during Exercise 2 they will create these structs.
12. In **DataSource.cs**, show them the **DataSource** class which populates the
    structs.
13. Open **MainWindow.xaml** and scroll to the view definitions in the XAML
    code.
14. Explain to students how the events are connected to the methods in each of
    the page definitions.
15. In the **Views** folder, open **LogonPage.xaml.cs**, and locate the
    **Logon_Click** event handler.
16. Explain to students that during Exercise 3 they will add this code to
    validate the user, assess whether they are a teacher or student, save their
    details, and then raise the **LogonSuccess** method.
17. Explain that if the user is not valid, the event handler raises the
    **LogonFailed**.
18. In **MainWindow.xaml.cs**, show students the **Logon_Success** and
    **Logon_Failed** event handlers.
19. In **MainWindow.xaml.cs**, locate the **Refresh** event and explain to
    students that during Exercise 3 they will add code to this method to display
    the user name in the Welcome message.
20. In **StudentsPage.xaml.cs**, locate the **Refresh** method, and explain to
    students that during Exercise 3 they will add this code to find all the
    students for the current teacher and bind them to a list on the view.
21. In **StudentsPage.xaml**, locate the **ItemsControl.ItemTemplate** element
    and explain that the databinding of the **Button** elements displays the
    student names on the buttons on the view.
22. Close Visual Studio.




©2018 Microsoft Corporation. All rights reserved.

The text in this document is available under the  [Creative Commons Attribution 3.0 License](https://creativecommons.org/licenses/by/3.0/legalcode), additional terms may apply. All other content contained in this document (including, without limitation, trademarks, logos, images, etc.) are  **not**  included within the Creative Commons license grant. This document does not provide you with any legal rights to any intellectual property in any Microsoft product. You may copy and use this document for your internal, reference purposes.

This document is provided &quot;as-is.&quot; Information and views expressed in this document, including URL and other Internet Web site references, may change without notice. You bear the risk of using it. Some examples are for illustration only and are fictitious. No real association is intended or inferred. Microsoft makes no warranties, express or implied, with respect to the information provided here.