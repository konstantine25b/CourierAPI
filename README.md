# CourierAPI

CourierAPI is a Django-based RESTful API designed to manage parcel delivery services. It provides endpoints to handle user authentication, parcel creation, and delivery proof submission. Below is a guide on how to set up and use the CourierAPI.

## Setting Up

1. **Clone the Repository**: Clone the CourierAPI repository to your local machine.

    ```bash
    git clone https://github.com/konstantine25b/CourierAPI
    ```

2. **Install Dependencies**: Navigate to the project directory and install the required dependencies.

    ```bash
    cd CourierAPI
    pip install -r requirements.txt
    ```

3. **Database Setup**: Configure the database settings in `settings.py`. By default, CourierAPI uses SQLite. You can change it to your preferred database management system.

4. **Migrate Database**: Apply migrations to create necessary database tables.

    ```bash
    python manage.py migrate
    ```

5. **Create Superuser**: Create a superuser to access the Django admin panel.

    ```bash
    python manage.py createsuperuser
    ```

6. **Run the Server**: Start the Django development server.

    ```bash
    python manage.py runserver
    ```

7. **Access Admin Panel**: Visit `http://127.0.0.1:8000/admin` in your browser and log in with the superuser credentials to access the admin panel.

## API Endpoints

CourierAPI provides the following endpoints:

- **Users**: Endpoint for managing users (registration, authentication).

    - `/api/users/`: (GET, POST) - Get a list of users or register a new user.

- **Parcels**: Endpoint for managing parcels.

    - `/api/parcels/`: (GET, POST) - Get a list of parcels or create a new parcel.
    - `/api/parcels/<parcel_id>/`: (GET, PUT, DELETE) - Retrieve, update, or delete a specific parcel.

- **Delivery Proof**: Endpoint for submitting delivery proof.

    - `/api/delivery-proofs/`: (GET, POST) - Get a list of delivery proofs or submit a new delivery proof.
    - `/api/delivery-proofs/<proof_id>/`: (GET, PUT, DELETE) - Retrieve, update, or delete a specific delivery proof.

## Authentication

CourierAPI uses token-based authentication. To access protected endpoints, clients must include an authentication token in the request header. Tokens can be obtained by authenticating a user through the `/api/token/` endpoint.
