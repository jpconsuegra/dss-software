# Devcontainer for DSS

Instructions to setup _Laravel_ project:

- Reopen project in DevContainer.

- Run `laravel new example-app`

    - Say no to `Default database updated. Would you like to run the default database migrations?`.
    > Optional: Use `php artisan migrate` after completing the project setup.

- Substitute the following inside the `example-app/.env`.

    ```
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=dss
    DB_USERNAME=dss
    DB_PASSWORD=dss
    ```

- Add the following to `example-app/vite.config.js`.

    ```js
    export default defineConfig({
        // ...
        server: {
            host: '0.0.0.0', // Listen on all network interfaces
            hmr: {
                host: 'localhost', // Ensure HMR points back to your host machine
            },
            // ...
        },
        // ...
    });
    ```

- Run `cd example-app`.

- Run `npm install && npm run build`.

- Run `composer run dev`.