# Dynamic-banner-website
A dynamic banner website built with React that allows users to update banner content such as description, timer, and visibility. The backend is powered by Node.js and MySQL, providing a seamless experience for managing and displaying dynamic content.
# Dynamic Banner Website

## Overview
The Dynamic Banner Website is a React-based application that allows users to update and manage banner content dynamically. The website includes an internal dashboard where administrators can modify the banner's description, timer, link, and visibility status. The backend is powered by Node.js and MySQL, with the database hosted on Render for seamless deployment and scalability.

## Features
- **Dynamic Banner Content**: Update banner description, timer, link, and visibility in real-time.
- **Internal Dashboard**: A secure interface to manage the banner content easily.
- **Backend**: Built with Node.js, using MySQL for data storage, and deployed on Render.
- **Frontend**: Built with React, styled with custom CSS, and deployed on Netlify.

## Demo
- **Live Website**: [Dynamic Banner Website](https://benevolent-frangipane-289601.netlify.app/)
- **Admin Dashboard**: [Admin Dashboard](https://beamish-truffle-2a01d6.netlify.app/)

## Getting Started

### Prerequisites
- Node.js (v14 or later)
- npm or yarn
- MySQL database

### Setting Up the Backend

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/your-username/dynamic-banner-website.git
    cd dynamic-banner-website
    ```

2. **Install Dependencies**:
    ```bash
    cd backend
    npm install
    ```

3. **Configure the Database**:
   - Create a MySQL database named `bannerDB`.
   - In the `.env` file, add your MySQL credentials:
     ```plaintext
     DB_HOST=<your-database-host>
     DB_USER=<your-database-username>
     DB_PASSWORD=<your-database-password>
     DB_NAME=bannerDB
     ```
   - Migrate the database schema:
     ```bash
     npx sequelize-cli db:migrate
     ```

4. **Run the Backend Server**:
    ```bash
    npm start
    ```
   - The backend server will start on `http://localhost:10000`.

### Setting Up the Frontend

1. **Navigate to Frontend Directory**:
    ```bash
    cd ../frontend
    ```

2. **Install Dependencies**:
    ```bash
    npm install
    ```

3. **Update Axios Endpoint**:
   - In `src/Dashboard.js`, update the Axios endpoint to point to your deployed backend on Render:
     ```javascript
     const fetchBannerContent = () => {
       axios.get('https://your-backend-url.onrender.com/api/banner')
         .then(response => {
           setBannerContent(response.data);
           setCurrentTimer(response.data.timer);
         })
         .catch(err => console.error(err));
     };
     ```

4. **Run the Frontend**:
    ```bash
    npm start
    ```
   - The frontend will be available on `http://localhost:3000`.

### Deployment

#### Deploying the Backend on Render

1. **Connect to Render**:
   - Create a Render account and link your GitHub repository.
   - Set up a new Web Service for your backend.

2. **Environment Variables**:
   - Add your MySQL credentials as environment variables on Render:
     - `DB_HOST`
     - `DB_USER`
     - `DB_PASSWORD`
     - `DB_NAME`

3. **Deploy**:
   - Deploy the backend service on Render
   - ![Screenshot (360)](https://github.com/user-attachments/assets/029faa9e-c9fd-4724-a61c-5330545d918b)


#### Deploying the Frontend on Netlify

1. **Connect to Netlify**:
   - Create a Netlify account and link your GitHub repository.

2. **Build and Deploy**:
   - Set up a new site on Netlify.
   - Configure the build command and publish directory:
     ```plaintext
     Build Command: npm run build
     Publish Directory: build
     ```

3. **Deploy**:
   - Deploy the frontend on Netlify.

### Usage

- **Access the Dynamic Banner Website**:
   - Visit the live website to see the dynamic banner in action.

- **Use the Admin Dashboard**:
   - Access the internal dashboard to manage the banner content.

## Contributing
Contributions are welcome! Please open an issue or submit a pull request with your improvements.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
