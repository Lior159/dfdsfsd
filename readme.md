<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Communication Ltd Project - README</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        line-height: 1.6;
        margin: 20px;
        padding: 20px;
        background-color: #f4f4f4;
      }
      pre {
        background-color: #eee;
        padding: 10px;
        border-radius: 5px;
      }
      code {
        font-family: "Courier New", Courier, monospace;
      }
      .container {
        max-width: 800px;
        margin: 0 auto;
        background-color: #fff;
        padding: 20px;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      }
      h1,
      h2,
      h3 {
        color: #333;
      }
      a {
        color: #0066cc;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>Communication Ltd Project</h1>
      <p>
        Follow the instructions below to set up the project on your local
        machine.
      </p>

      <h2>Prerequisites</h2>
      <p>
        Before you begin, ensure you have the following installed on your
        system:
      </p>
      <ul>
        <li>SQL Server</li>
        <li>Node.js and npm</li>
      </ul>

      <h2>Setting Up the Project</h2>

      <h3>Step 1: Set Up the SQL Server Database</h3>
      <ol>
        <li>
          <p><strong>Create a new database:</strong></p>
          <p>Name the database <code>comunication_ltd</code>.</p>
        </li>
        <li>
          <p><strong>Create the required tables:</strong></p>
          <p>
            Open SQL Server Management Studio (SSMS) or any SQL query tool you
            prefer. Run the following SQL scripts to create the necessary
            tables:
          </p>
          <pre><code>-- Create sessions table
CREATE TABLE sessions (
    sid NVARCHAR(255) NOT NULL,
    session NVARCHAR(MAX) NOT NULL,
    expires DATETIME NOT NULL,

    PRIMARY KEY (sid)
);
    
-- Create users table
CREATE TABLE users (
    uname VARCHAR(100) NOT NULL,
    password VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    created_at DATETIME NOT NULL,
    status VARCHAR(100) NOT NULL,
    otp VARCHAR(100) NULL,
    otp_expire DATETIME NULL,

    PRIMARY KEY (uname, created_at)
);

-- Create users customers
CREATE TABLE customers (
    id VARCHAR(100) NOT NULL,
    full_name NVARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    phone VARCHAR(100) NOT NULL,
    birth_date DATE NOT NULL,
    gender VARCHAR(100) NOT NULL,
    street NVARCHAR(100) NOT NULL,
    city NVARCHAR(100) NOT NULL,
    post_code VARCHAR(100) NOT NULL,
    created_by VARCHAR(100) NOT NULL,

    PRIMARY KEY (id),
    FOREIGN KEY (created_by) REFERENCES users(uname)
);  
            </code></pre>
        </li>
      </ol>

      <h3>Step 2: Configure Environment Variables</h3>
      <p>
        Create a <code>.env</code> file in the root directory of your project
        and add the following fields:
      </p>
      <pre><code>DB_SERVER=&lt;your_sql_server&gt;
DB_DATABASE=comunication_ltd
DB_USER=&lt;your_database_user&gt;
DB_PASSWORD=&lt;your_database_password&gt;
DB_PORT=&lt;your_database_port&gt;
SERVER_PORT=&lt;your_server_port&gt;
SESSION_SECRET=&lt;your_session_secret&gt;
GMAIL_USERNAME=&lt;your_gmail_username&gt;
GMAIL_APP_PASSWORD=&lt;your_gmail_app_password&gt;</code></pre>
      <p>Replace the placeholders with your actual configuration values.</p>

      <h3>Step 3: Install Dependencies</h3>
      <p>
        Run the following command in the root directory of your project to
        install the necessary dependencies:
      </p>
      <pre><code>npm install</code></pre>

      <h2>Running the Project</h2>
      <p>
        After setting up the database and configuring the environment variables,
        you can start the server with the following command:
      </p>
      <pre><code>npm start</code></pre>
      <p>
        Your server should now be running on the port specified in the
        <code>.env</code> file (<code>SERVER_PORT</code>).
      </p>

      <h2>Contact</h2>
      <p>
        If you have any questions or need further assistance, feel free to
        contact us at
        <a href="mailto:liorzalta24@gmail.com">liorzalta24@gmail.com</a>.
      </p>
    </div>
  </body>
</html>
