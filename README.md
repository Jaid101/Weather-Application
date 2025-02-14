
### 📌 **Weather Application Documentation**  

## 📖 **Overview**  
The Weather Application is an Android app that fetches real-time weather data using the OpenWeather API. It allows users to search weather conditions by city name or current location. The app is built using **Retrofit for networking**, **Picasso for image loading**, and **Lottie for animations**.  

---

## 🛠 **Tech Stack & Libraries**  

| Component      | Technology Used |
|---------------|----------------|
| **Language**  | Java |
| **UI Framework** | Android SDK, Material UI |
| **Network Requests** | Retrofit 2 |
| **JSON Parsing** | Gson |
| **Image Loading** | Picasso |
| **Animations** | Lottie |
| **Location Services** | Google Play Services |

---

## 🚀 **Project Setup**  

### **1️⃣ Clone the Repository**
```sh
git clone https://github.com/your-repo/weather-app.git
cd weather-app
```

### **2️⃣ Open in Android Studio**  
- Open **Android Studio**
- Select **Open an Existing Project**  
- Navigate to the cloned folder and open it.  

### **3️⃣ Add API Key in `Constants.java`**  
Create a `Constants.java` file inside `util` package and add:  
```java
package com.example.weatherapplication.util;

public class Constants {
    public static final String BASE_URL = "https://api.openweathermap.org/data/2.5/";
    public static final String SUB_URL = "weather?appid=YOUR_API_KEY&units=metric";
}
```
**👉 Replace `YOUR_API_KEY` with your actual OpenWeather API key.**  

### **4️⃣ Sync Dependencies**  
Ensure all dependencies are installed by syncing Gradle:  
- Open `build.gradle.kts`  
- Click **"Sync Now"** in Android Studio.  

---

## 📲 **App Features**  

✅ Fetch weather data by **city name**  
✅ Fetch weather data using **current location (latitude & longitude)**  
✅ Display **temperature, humidity, wind speed, and weather description**  
✅ Show weather **icons using Picasso**  
✅ **Swipe to refresh** for updated weather  
✅ **Lottie animations** for smooth UI  

---

## 🌐 **API Endpoints**  

| API | Endpoint | Parameters |
|-----|----------|------------|
| **Get Weather by City** | `/weather` | `q={city_name}` |
| **Get Weather by Location** | `/weather` | `lat={latitude}&lon={longitude}` |

**Example Request:**  
```plaintext
https://api.openweathermap.org/data/2.5/weather?q=Mumbai&appid=YOUR_API_KEY&units=metric
```

**Example Response:**
```json
{
  "coord": { "lon": 72.85, "lat": 19.01 },
  "weather": [{ "main": "Clouds", "description": "broken clouds", "icon": "04d" }],
  "main": { "temp": 30.0, "pressure": 1012, "humidity": 70 },
  "wind": { "speed": 5.0, "deg": 220 },
  "name": "Mumbai"
}
```

---

## 📜 **Code Structure**  

```
📦 com.example.weatherapplication
 ┣ 📂 Service
 ┃ ┣ 📜 WeatherApi.java         # Retrofit API calls
 ┃ ┗ 📜 RetrofitInstance.java   # Singleton Retrofit instance
 ┣ 📂 model
 ┃ ┗ 📜 WeatherModel.java       # Data model for API response
 ┣ 📂 util
 ┃ ┗ 📜 Constants.java          # API URL & keys
 ┣ 📜 MainActivity.java         # Main activity with UI
 ┣ 📜 AndroidManifest.xml       # Permissions & app config
 ┗ 📜 build.gradle.kts          # Dependencies & build setup
```
📲 App Features
✅ Fetch weather data by city name and current location
✅ Display temperature, humidity, wind speed, and weather description
✅ Show weather icons using Picasso
✅ Swipe to refresh for updated weather
✅ Lottie animations for smooth UI
✅ Error handling mechanisms for network and location issues:

Network Error Handling
Checks if the device is connected to the internet before making an API request.
Displays an error message if no internet connection is available.
Handles API failures by showing an error toast and retry option.
Location Error Handling
Checks if GPS/location services are enabled before fetching weather data.
Requests location permissions dynamically at runtime.
Displays an alert dialog if location permission is denied.
Uses a default city (fallback mechanism) if location access is not granted.
Handles GPS signal loss by displaying a message and allowing manual city input.
---

## 📌 **Permissions Required**  
Open `AndroidManifest.xml` and ensure the following permissions are added:  
```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
```
The app requires **Internet** to fetch weather data and **Location permissions** to get current weather.

---

## 🏃 **How to Use the App?**  
1️⃣ Open the app.  
2️⃣ **Enter a city name** or enable **GPS location**.  
3️⃣ Click **Search** to fetch weather details.  
4️⃣ Swipe down to **refresh**.  

---

## 🛠 **Troubleshooting & FAQs**  

❓ **App crashes on launch**  
🔹 Make sure you have added a valid **API key** in `Constants.java`.  

❓ **Weather not updating?**  
🔹 Ensure **internet is connected** and **location services** are enabled.  

❓ **Gradle build failed?**  
🔹 Try running:
```sh
./gradlew clean build
```

---

## 📜 **Future Enhancements**  
🔹 Add **Hourly & Weekly Forecast**  
🔹 Support for **multiple languages**  
🔹 Dark mode support 🌙  

---

## 💙 **Contributing**  
- Fork the repo  
- Create a new branch (`feature-branch`)  
- Submit a pull request 🚀  

