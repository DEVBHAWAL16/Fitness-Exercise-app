# React Fitness Application
A React-based web application for discovering and tracking fitness exercises. Built with Material UI, React Router, and a public exercise API, this app lets users:

-  Search exercises by name or body part  
-  Browse curated lists of exercises  
-  View detailed information (images, target muscle, equipment) for each exercise  
-  Enjoy a responsive, mobile-friendly interface  


![React Fitness Application](https://i.ibb.co/Yt9spGc/image.png)


## Key Features

- **Search & Filter**  
  - Full-text search by exercise name  
  - Filter exercises by body part (e.g. chest, legs, arms)  
- **Exercise Detail Pages**  
  - High-quality GIFs or images demonstrating each exercise  
  - Target muscle group and equipment needed  
- **Responsive Design**  
  - Mobile-first layout using Material UI’s Grid and Box components  
- **Smooth Navigation**  
  - React Router for client-side page transitions  
  - Scroll-to-top behavior on route change 

## Tech Stack

- **React** (v18)  
- **Material UI** (v5) for UI components  
- **React Router** (v6) for routing  
- **react-horizontal-scrolling-menu** for horizontal carousels  
- **react-loader-spinner** for loading indicators  
- **ESLint** (Airbnb style guide) for code linting  


## Getting Started

### Prerequisites

- Node.js (>=14.x) & npm  
- Optional: Yarn  

### Installation

1. **Clone the repo**  
   git clone https://github.com/DEVBHAWAL16/Fitness-Exercise-app.git
   cd Fitness-Exercise-app

2. **Install dependencies**
   npm install
   # or
   yarn install
   

3. **Add your API credentials**

   * Create a `.env` file in the root:
     REACT_APP_RAPIDAPI_KEY=your_rapidapi_key_here
   
   * (You can obtain a free key from [RapidAPI’s ExerciseDB](https://rapidapi.com/justin-WFnsXH_t6/api/exercisedb).)

### Running Locally
npm start
# or
yarn start

Your app will be available at `http://localhost:3000`.

## Project Structure

Fitness-Exercise-app/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── components/
│   │   ├── Exercises.jsx
│   │   ├── ExerciseCard.jsx
│   │   ├── Footer.jsx
│   │   ├── HeroBanner.jsx
│   │   ├── Navbar.jsx
│   │   └── SearchExercises.jsx
│   ├── pages/
│   │   ├── Home.jsx
│   │   └── ExerciseDetail.jsx
│   ├── App.css
│   ├── App.js
│   ├── index.js
│   └── utils/
│       └── fetchData.js
├── .env
├── package.json
└── README.md


## Component Overview

* **`Navbar.jsx`**
  Top navigation bar with app branding and links.

* **`HeroBanner.jsx`**
  Full-width banner on the Home page with call-to-action.

* **`SearchExercises.jsx`**
  Search input + body-part filter buttons.

* **`Exercises.jsx`**
  Displays a paginated list of `ExerciseCard` components.

* **`ExerciseCard.jsx`**
  Individual exercise preview (image, name, target muscle).

* **`ExerciseDetail.jsx`**
  Detailed view: exercise GIF, description, muscle/equipment info.

* **`Footer.jsx`**
  Site footer with links and attribution.

* **`fetchData.js`**
  Centralized API fetch helper using `fetch` + RapidAPI headers.



## API Integration

We use **ExerciseDB** via **RapidAPI**:

* **Endpoints:**

  * `GET /exercises` → list all exercises
  * `GET /exercises/bodyPart/{bodyPart}` → filter by body part
  * `GET /exercises/exercise/{id}` → details for one exercise

js
// utils/fetchData.js
export const fetchData = async (url, options) => {
  const response = await fetch(url, options);
  const data = await response.json();
  return data;
};

Add your key in `.env`:

REACT_APP_RAPIDAPI_KEY=YOUR_KEY
REACT_APP_RAPIDAPI_HOST=exercisedb.p.rapidapi.com


## Styling & Layout

* Material UI’s **`Box`**, **`Stack`**, and **`Typography`** for responsive layouts.
* Global CSS overrides in `App.css` for minor custom tweaks.
* **react-horizontal-scrolling-menu** for horizontal carousels of body-part buttons.

## Future Enhancements

*  User authentication & favorites list
*  Track workout history & stats
*  Dark/light mode toggle
*  Shareable workout plans
*  Multi-language support
