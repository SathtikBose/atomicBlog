# ⚛️ The Atomic Blog

A modern, high-performance React blog application demonstrating advanced state management patterns, mock data generation, and a unique "fake dark mode" implementation.

[![Live Demo](https://img.shields.io/badge/demo-online-brightgreen.svg)](https://sathtikbose.github.io/atomicBlog/)
[![React](https://img.shields.io/badge/React-18.2.0-blue.svg)](https://reactjs.org/)
[![Context API](https://img.shields.io/badge/State-Context%20API-61dafb.svg)](https://reactjs.org/docs/context.html)
[![Faker.js](https://img.shields.io/badge/Data-Faker.js-ff69b4.svg)](https://fakerjs.dev/)

## 🚀 Overview

**The Atomic Blog** is a small yet powerful demonstration of building scalable React applications. It focuses on the "Atomic" philosophy—breaking down UI into small, reusable components—while handling large amounts of data efficiently.

The application features a real-time search engine, a dynamic post archive with over 10,000 entries, and a sleek dark mode toggle that utilizes CSS filters for an instant aesthetic shift.

## ✨ Key Features

-   **Dynamic Post Management**: Create new posts instantly or clear the entire feed with a single click.
-   **Real-time Search**: Instant filtering of posts as you type, powered by derived state logic.
-   **Massive Post Archive**: Explore a secondary archive containing 10,000+ posts generated on-the-fly using `Faker.js`.
-   **State Management**: Optimized using the **React Context API** with a custom `usePosts` hook to avoid prop drilling.
-   **Fake Dark Mode**: A unique implementation using a 100% inversion filter on the document root for a seamless theme switch.
-   **Performance Focused**: Implements state memoization tricks (functional updates and initial state callbacks) to keep the UI responsive even with 10k+ elements.

## 🛠️ Tech Stack

-   **Frontend**: React 18
-   **State Management**: Context API (Provider/Consumer pattern)
-   **Data Generation**: Faker.js (@faker-js/faker)
-   **Styling**: Pure CSS3 (Flexbox & CSS Grid)
-   **Deployment**: GitHub Pages

## 📦 Installation & Setup

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/SathtikBose/atomicBlog.git
    cd atomicBlog
    ```

2.  **Install dependencies**:
    ```bash
    npm install
    ```

3.  **Start the development server**:
    ```bash
    npm start
    ```
    The app will be available at `http://localhost:3000`.

## 📂 Project Structure

```text
src/
├── App.js            # Main application component & layout
├── PostContext.js    # Global state management & custom hooks
├── index.js          # Entry point
├── style.css         # Custom styling & dark mode logic
└── Test.js           # Experimental components/Testing
```

## 💡 Implementation Details

### The "Fake" Dark Mode
Instead of traditional theme variables, this project uses a CSS-only inversion trick:
```css
.fake-dark-mode {
  filter: invert(100%);
  transition: all 0.5s;
}
```
This is toggled globally in `App.js` via a `useEffect` hook that watches the `isFakeDark` state.

### Context API Optimization
The application avoids performance bottlenecks by encapsulating all post-related logic within `PostProvider`. Components consume only the data they need via the `usePosts()` hook, ensuring a clean and maintainable codebase.

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---
Built with ⚛️ by [Sathtik Bose](https://github.com/SathtikBose)
