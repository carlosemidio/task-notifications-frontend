# task-notifications

## Project Setup
Follow these steps to run the project:

1. **Copy the environment file**  
    Duplicate the `.env.example` file and rename it to `.env`:
    ```sh
    cp .env.example .env
    ```

2. **Set the API URL**  
    Open the `.env` file and set the `VITE_API_URL` variable to the tasks list API endpoint:
    ```env
    VITE_API_URL=https://your-tasks-list-api-endpoint.com
    ```

### Using npm:

1. **Install dependencies**  
    Run the following command to install the required dependencies:
    ```sh
    npm install
    ```

2. **Start the development server**  
    To compile and hot-reload the project for development, use:
    ```sh
    npm run dev
    ```

3. **Build for production**  
    To compile and minify the project for production, execute:
    ```sh
    npm run build
    ```

4. **Preview the production build**  
    To locally preview the production build, run:
    ```sh
    npm run preview
    ```

### Using Yarn:

1. **Install dependencies**  
    Run the following command to install the required dependencies:
    ```sh
    yarn
    ```

2. **Start the development server**  
    To compile and hot-reload the project for development, use:
    ```sh
    yarn dev
    ```

3. **Build for production**  
    To compile and minify the project for production, execute:
    ```sh
    yarn build
    ```

4. **Preview the production build**  
    To locally preview the production build, run:
    ```sh
    yarn preview
    ```
    
5. **Access the application**  
        Once the development server is running, you can access the application in your browser at:  
        [http://localhost:5173/](http://localhost:5173/) 
