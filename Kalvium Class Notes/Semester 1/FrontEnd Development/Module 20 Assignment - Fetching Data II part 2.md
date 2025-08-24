# 📘 Study Notes: Fetching Data II – Part 2 (Weather App with API)

## 🎯 Objective

- Apply **JavaScript concepts** to build a **smartwatch project**.
- Fetch and display **real-time weather data** from **OpenWeatherMap API**.

---

## 🏗️ Steps to Implement

### 1. Get API Key

- Create account at 👉 [openweathermap.org](https://openweathermap.org/).
- Go to **Profile → Settings → API Keys**.
- Copy your **API key** (needed for requests).

---

### 2. API Endpoint Format

```http
https://api.openweathermap.org/data/2.5/weather?q={city name}&appid={API key}&units=metric
```

- `q=` → city name (e.g., London).
- `appid=` → your API key.
- `units=metric` → temperature in °C.

---

### 3. Fetch Weather Data with `fetch()`

```js
async function getWeather(city) {   try {     const response = await fetch(       `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=YOUR_API_KEY&units=metric`     );      if (!response.ok) throw new Error("API Error: " + response.status);      const data = await response.json();      // Extract values     const temp = data.main.temp;     const desc = data.weather[0].description;     const cityName = data.name;      // Update UI     document.getElementById("city").textContent = cityName;     document.getElementById("temp").textContent = `${temp} °C`;     document.getElementById("desc").textContent = desc;    } catch (error) {     console.error("Error fetching weather:", error);   } }

```
---

### 4. UI Integration

- Call `getWeather("Delhi")` or any city.
- Display values in **smartwatch-like UI**.

---

## 🚨 Error Handling

- Invalid API key → error 401.
- City not found → error 404.
- Use `try...catch` to handle gracefully.

---

## ✅ Submission

- Implement code in editor.
- Ensure UI matches expected output.
- Run provided tests if any.

---

# 📌 Cheat Sheet

- **Get API key** → from openweathermap.org → profile → API keys.
- **API URL**
```http
https://api.openweathermap.org/data/2.5/weather?q={city}&appid={API_KEY}&units=metric
```
- **Fetch Weather** (async/await)
```js
const res = await fetch(url); 
const data = await res.json();
```
**Extract Values**
```js
- data.main.temp → temperature
- data.weather[0].description → weather status
- data.name → city name
```
- **Errors**
    - 401 → Wrong API key
    - 404 → City not found