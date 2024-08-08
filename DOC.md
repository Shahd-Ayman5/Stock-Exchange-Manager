> # Documentation

### HelloApplication Class
This `HelloApplication` class serves as the entry point for your JavaFX application. Here’s a breakdown of what it does:
- It extends the `Application` class provided by JavaFX.
- The `start()` method is overridden to set up the primary stage (window) of the application. Inside this method:
  - It loads the FXML file `hello-view.fxml` using a `FXMLLoader`.
  - Creates a scene with the loaded FXML content, setting its dimensions to 600x400 pixels.
  - Sets the title of the stage to “Hello!”.
  - Sets the scene to the stage and displays the stage.
- The `main()` method is the entry point of the application. It launches the JavaFX application by calling the `launch()` method inherited from the `Application` class.

### HelloController Class
This `HelloController` class is responsible for controlling the logic behind the “Hello!” application. Here’s a breakdown of what it does:
- It handles various actions and events triggered by user interactions in the application’s UI.
- It contains methods for transitioning between different scenes in the application.
- It interacts with the `User` class to manage user data, such as registration, login, and logout.
- It manages the initialization of UI elements and handles user inputs, such as username, password, and gender selection.
- It writes user data to a text file (`csv.txt`) when a new user registers.

### sellStocks Class
This class, named `sellStocks`, represents the process of selling stocks. It has two private variables: `price` and `quantity`. These variables are initialized through the constructor method `sellStocks`, which takes the price and quantity as parameters.
- Getter and setter methods are provided for both price and quantity, allowing access to their values and modification from other parts of the code in the project.

### TimerManager Class
This is the `TimerManager` class, responsible for managing a timer in the application. It utilizes JavaFX’s AnimationTimer for timing purposes.
- The class has instance variables `timer` and `elapsedTime`, representing the timer itself and the elapsed time, respectively. It also includes static boolean variables `timeon` and `timeoff` to track the timer’s state.
- The constructor initializes the `elapsedTime` property and sets up the `timer` AnimationTimer to calculate the elapsed time.
- The `start()` method starts the timer by setting the start time using `System.nanoTime()` and starting the timer itself. It also updates the `timeon` and `timeoff` flags accordingly.
- The `stop()` method stops the timer and updates the `timeon` and `timeoff` flags.
- The `elapsedTimeProperty()` method returns the `elapsedTime` property for external access.
- The `getInstance()` method is implemented as a singleton pattern to ensure only one instance of `TimerManager` is created throughout the application.

### UserController Class
This class, named `UserController`, manages user interactions in the application. It contains various methods and fields to handle user actions such as depositing money, withdrawing money, logging out, navigating between different views, and more.
- Includes JavaFX annotations such as `@FXML` to mark fields and methods that are associated with elements in the user interface defined in an FXML file.
- The `initialize()` method initializes the timer when the controller is created.
- The `add()` method updates the displayed balance.
- Methods like `calc_deposit()` and `calc_withdraw()` update the user’s balance based on deposit and withdrawal actions.
- The `changeBalance()` method handles the logic for depositing and withdrawing money, updating the balance, and adding orders to the order list.
- The `updateTimer()` method updates the displayed timer.
- Methods like `goToUserHistory()`, `goToProf()`, `buy()`, `sell()`, and `chart()` handle navigation to different parts of the application.
- The `setUserProf()` method sets user profile information.
- Orchestrates the behavior of the user interface and interacts with other parts of the application to perform various actions based on user input.

### CompanyController Class
This class, named `CompanyController`, manages interactions related to companies in the application. It handles functionalities such as buying and selling stocks, displaying company details, and navigating to different views.
- Includes JavaFX annotations such as `@FXML` to mark fields and methods associated with elements in the user interface defined in an FXML file.
- The `initialize()` method initializes the ComboBoxes and sets up the timer.
- The `updateTimer()` method updates the displayed timer.
- Methods like `goHome()`, `sell()`, and `buy()` handle navigation to different parts of the application.
- The `setUserDetails()` and `setStockDetails()` methods set details for buying and selling stocks respectively.
- Methods like `setCompany1()`, `setCompany2()`, and `setCompany3()` set the displayed details for companies.
- Manages ArrayLists to store company and stock information, and it updates the displayed information based on user actions.
- The `com_Initialize()` method initializes company data, including price, quantity, and open/close values.
- The `companies()` method updates the displayed details for companies.
- The `calc_Change()` method calculates the change in stock prices.
- Methods like `setStock1()`, `setStock2()`, and `setStock3()` set the displayed details for stocks.
- The `stocks()` method updates the displayed details for stocks.
- Includes methods for buying and selling stocks, such as `setComValue()` and `setStockValue()`, which update the quantity and price of stocks based on user actions.

### User Class
This class, named `User`, represents user data in the application. Here’s an overview of its key features:
- Contains private fields for user attributes such as first name, last name, email, password, gender, and balance.
- The `User` class includes a constructor to initialize user objects with all the necessary attributes.
- Getter and setter methods are provided for each attribute to access and modify the user data.
- The balance field is marked as static, meaning it belongs to the class itself rather than individual instances of the class. This allows for easy access and modification of the balance across different parts of the application.
- The `setBalance()` method is a static method used to set the balance value.

### sellCompany Class
This class, named `sellCompany`, represents data related to selling a company’s stock. Here’s a summary of its structure and functionality:
- Contains private fields to store information about the price, quantity, open value, and close value of a company’s stock.
- The class includes a constructor to initialize objects of this type with the specified attributes.
- Getter and setter methods are provided for each attribute to access and modify the data as needed.
- The `getPrice()`, `getQuantity()`, `getOpen()`, and `getClose()` methods return the corresponding values of the fields.
- Similarly, the `setPrice()`, `setQuantity()`, `setOpen()`, and `setClose()` methods allow for updating the values of these fields.

### sellStocksController Class
This class, `sellStocksController`, manages the selling of stocks. Here’s a summary of its functionality:
- Includes private fields for JavaFX elements such as labels and combo boxes.
- The class contains a method named `initialize()` that is called when the FXML file is loaded. This method sets up the combo boxes with options for selecting the company to sell stocks and the quantity to sell.
- There’s a method `updateTimer()` to update a timer label based on the elapsed time.
- The `goHome()` method is responsible for navigating back to the user page when the corresponding button is clicked. It retrieves the current stage, sets a new scene with the user page, and shows the stage.

### StockController Class
The `StockController` class is associated with managing stock-related information in the application. Here’s what it does:
- Contains labels to display information related to stock changes, closing prices, and opening prices.
- Has a method `isUser(ActionEvent event)` that is likely triggered when the user interacts with the associated UI element. This method calls the `goToUserscreen(ActionEvent event)` method from the `HelloController` class and then sets the opening prices for the stocks.
- The line `HelloController price = new HelloController();` creates a new instance of `HelloController`, which might not be the intended behavior. Usually, controllers are managed by the JavaFX framework, and you don’t create instances of them manually. Instead, you’d obtain a reference to an existing controller instance that’s already managing the scene.

### OrderController Class
The `OrderController` class manages orders in the application. Here’s a breakdown of its functionality:
- Contains labels to display information about orders, such as user names, order types, and amounts.
- The `setOrder` method sets the order details based on the user ID.
- Methods `setOrder1`, `setOrder2`, `setOrder3`, and `setOrder4` set the details for each order.
- Approval methods `approve1`, `approve2`, `approve3`, and `approve4` are associated with approving orders. These methods remove the approved order from the order list and trigger the `approve` method to calculate deposit or withdrawal.
- The `approve` method calculates deposit or withdrawal based on the approval status. It then updates the UI and navigates to the transaction orders page.

### ChartsController Class
The `ChartsController` class manages the display of line charts in the application. Here’s an overview of its functionality:
- Initializes the line charts and updates them with data when the `initialize` method is called.
- The `updateTimer` method formats and updates the timer label with the elapsed time.
- In the `initialize` method, if the `TimerManager` indicates that the time is up (`TimerManager.timeoff`), it populates the line charts with data from `CompanyController.price_arr`, `CompanyController.price_arr2`, and `CompanyController.price_arr3`.
- The `goHome` method allows users to navigate back to the user page when the corresponding button is clicked.

### Company Class
The `Company` class represents a company entity with attributes such as price, quantity, open, and close values. Here’s a summary of its functionality:
- Has instance variables to store the price, quantity, open, and close values of a company.
- The constructor initializes these variables with the values provided as arguments.
- Provides getter and setter methods to access and modify the values of these variables.
- Getter methods like `getPrice()`, `getQuantity()`, `getOpen()`, and `getClose()` return the respective attribute values.
- Setter methods like `setPrice()`, `setQuantity()`, `setOpen()`, and `setClose()` set the values of the respective attributes.

## Interactions Between Classes and Methods

1. **HelloController ↔ OrderController**:
   - Methods `approve1()`, `approve2()`, `approve3()`, and `approve4()` in `OrderController` are called after approving orders, which remove the approved order from `orderList`.

2. **OrderController ↔ UserController**:
   - When approving an order in `OrderController`, `calc_deposit()` or `calc_withdraw()` in `UserController` is called based on the approval status, which calculates deposit or withdrawal amounts.

3. **ChartsController ↔ CompanyController**:
   - `initialize()` in `ChartsController` is called to display data in the charts, which comes from `CompanyController` through arrays `price_arr`, `price_arr2`, and `price_arr3`.

4. **HelloController ↔ UserController**:
   - The balance value is added to `UserController` from `HelloController` when navigating between screens.

5. **StockController ↔ HelloController**:
   - Some interactions are simulated between the two classes, where `StockController` displays certain prices and then calls `goToUserscreen()` in `HelloController` upon clicking on a specific button.

Enjoy managing your stocks and exploring the various features of the Stock Exchange Manager!
