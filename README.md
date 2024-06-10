# Weather-
1.	Purpose of the App 
The overall purpose of the application is to satisfy a local weather organisation's needs by offering a user-friendly interface that shows the weekly weather conditions. It is to ensure that the viewing of weather data is easy and interactive for users. Users of the app will be able to examine the weekly average temperature as well as the specific weather forecast for each day. 
The application will have essential features that improve the user’s overall experience, namely how the weekly average temperature will be displayed. Users will also be able to navigate every day of the week to view precise weather details, such as the minimum and maximum temperatures as well as the overall weather conditions.

These are essential elements and Capabilities that will be found in the application.
•	Screen Summary for the Week: The computed average temperature for the week is displayed here. 
•	Comprehensive Weather Data: Give every day's lowest and maximum temperatures, together with detailed weather conditions, in one comprehensive file.
•	Navigation Buttons: Provide a button to go back to the weekly summary and buttons to travel to the day before and the day after.


2.	Pseudocode 

Start 
	Declarations 
  String weekDays [7] = [ “Monday”, “Tuesday”, “Wednesday”, “Thursday”, “Friday”, “Saturday”, “Sunday”]
	 num maxTemps []
	  num minTemps []
	  String weatherConditions [] 

 // Display the following in the Slash screen 
 Splash Screen ()
Output “The Weather Forecast App”
Display button "Enter App” // Navigates to Main Screen 
Display button “Exit”  // Exits the app 

    onClick(Navigate to Main Screen) {
        navigateTo(MainScreen)
    }

    onClick(Exit App) {
        exitApp()
    }
}

// MAIN SCREEN
function MainScreen {
    // Initialize Arrays
    array minTemps[7]
    array maxTemps[7]
    array weatherConditions[7]

    // Layout Elements
    display TextFields(Min Temp, Max Temp, Weather Condition) for each day
    display Button(Calculate Average Temperature)
    display Button(Navigate to Detailed View Screen)
    display Button(Clear Data)
    display Button(Exit App)
    display TextView(Average Temperature)

    onClick(Calculate Average Temperature) {
        call calculateAverageTemperature()
    }

    onClick(Navigate to Detailed View Screen) {
        navigateTo(DetailedViewScreen)
    }

    onClick(Clear Data) {
        call clearData()
    }

    onClick(Exit App) {
        exitApp()
    }

    function calculateAverageTemperature {
        sumMinTemps = 0
        sumMaxTemps = 0
        daysCount = 7

        for i = 0 to daysCount - 1 {
            sumMinTemps += minTemps[i]
            sumMaxTemps += maxTemps[i]
        }

        avgMinTemp = sumMinTemps / daysCount
        avgMaxTemp = sumMaxTemps / daysCount
        display TextView(Average Temperature).setText("Average Min Temp: " + avgMinTemp + ", Average Max Temp: " + avgMaxTemp)
    }

    function clearData {
        for i = 0 to 6 {
            minTemps[i] = 0
            maxTemps[i] = 0
            weatherConditions[i] = ""
        }

        clear TextFields
    }
}

// DETAILED VIEW SCREEN
function DetailedViewScreen {
    // Layout Elements
    for i = 0 to 6 {
        display TextView(Day i + 1, "Min Temp: " + minTemps[i] + ", Max Temp: " + maxTemps[i] + ", Condition: " + weatherConditions[i])
    }
    display Button(Navigate to Main Screen)

    onClick(Navigate to Main Screen) {
        navigateTo(MainScreen)
    }
}

// Function to handle navigation between screens
function navigateTo(screen) {
    switch(screen) {
        case MainScreen:
            // Load Main Screen Layout
            break
        case DetailedViewScreen:
            // Load Detailed View Screen Layout
            break
    }
}

// Function to exit the app
function exitApp() {
}
 End 
3.	 Images of the app

 
This is the first page of the app, where the user can then navigate to the main page once they have clicked the Enter app button. 
![image](https://github.com/LeloMakhoana/Weather-app/assets/166069329/7ff838de-5797-490b-ad7f-f288dfabcc6c)



 
The is the main screen of the app, where the user can check the weather by inputting values.

![image](https://github.com/LeloMakhoana/Weather-app/assets/166069329/2069e75f-4b96-4abd-ab97-3ae4ef2a9b39)

 
This is the last screen of the applicationn 
![image](https://github.com/LeloMakhoana/Weather-app/assets/166069329/de4d738a-045b-4547-b0c9-982a867a0945)




References 
https://eng.libretexts.org/Bookshelves/Computer_Science/Programming_and_Computation_Fundamentals/Programming_Fundamentals_-_A_Modular_Structured_Approach_using_C_(Busbee)/07%3A_Program_Control_Functions/7.01%3A_Psuedocode_Examples_for_Functions
https://tex.stackexchange.com/questions/48131/defining-a-function-in-pseudocode
