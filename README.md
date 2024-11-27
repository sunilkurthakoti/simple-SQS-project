# simple-SQS-project
simple SQS project with Node.js application

## **1. Create or Update the Node.js App Code Locally**

- Write or update your Node.js application to integrate with **AWS SQS (Simple Queue Service)**.
- Use **Express** to set up the server, and include endpoints for sending and receiving messages.
- Use the **AWS SDK** to configure SQS for sending and receiving messages.

![Screenshot (1)](https://github.com/user-attachments/assets/14b7fa32-069e-4540-b339-9c686d467df3)


## **2. Create an SQS Queue**

- Log in to the **AWS Console** and navigate to **SQS**.
- Create a new **SQS queue** with a meaningful name (e.g., `message-queue`).
- Choose between **Standard** and **FIFO** queues based on your requirements:
  - **Standard** queues allow high throughput but may deliver messages out of order.
  - **FIFO** queues guarantee message order but have limited throughput.
- Note down the **Queue URL** after creating the queue.

![Screenshot (2)](https://github.com/user-attachments/assets/b7594693-fcb8-4913-8323-2146a9c356d3)


## **3. Update the SQS Queue URL in the Code Locally**

- Copy the **Queue URL** of the newly created SQS queue from the AWS Console.
- In your Node.js application, replace the existing `QueueUrl` in the code with the new **Queue URL**.
- Save the changes to ensure the application uses the correct SQS queue.

## **4. Push the Code to GitHub**

- Initialize a Git repository in your project folder if you haven't already.
- Commit all the changes, including the updated SQS configuration.
- Push the code to a new or existing GitHub repository.
- Add a `.gitignore` file to exclude unnecessary files like `node_modules` and sensitive configuration files.

## **5. Create an EC2 Instance and Attach IAM Role**

- **Launch an EC2 Instance**: Go to the AWS Console and create an EC2 instance with your preferred operating system (e.g., Ubuntu).
-  **Attach an IAM Role**: Assign an IAM role to the EC2 instance with permissions for SQS access (e.g., `AmazonSQSFullAccess` policy).

 ![Screenshot (3)](https://github.com/user-attachments/assets/adc6cfbf-6da1-41e3-b45e-8bd431166f9b)

-  **Clone the GitHub Repository**: Once the instance is running, clone the GitHub repository containing your Node.js application.

 ![Screenshot (12)](https://github.com/user-attachments/assets/da85b824-48f3-4387-9fba-5f668756da23)

-  **Install Dependencies**:
   - Ensure **Node.js** and **npm** are installed.
   - Install required npm packages such as `pm2`, `express`, `aws-sdk`, `body-parser`, and `ejs`.
 
  ![Screenshot (15)](https://github.com/user-attachments/assets/09ae19cb-0328-428b-8384-d76e9bab541b)

-  **Start the Application**: Use **PM2** to run the application in the background for uninterrupted service.

![Screenshot (16)](https://github.com/user-attachments/assets/2c0e4c1c-b9da-46a5-9729-3b52ca68b716)


## **6. Access the Application in a Web Browser**

- Open a browser and navigate to the **public IP** of your EC2 instance.

![Screenshot (17)](https://github.com/user-attachments/assets/87627f0b-0dba-4808-b1c0-cf75e6dc6c2e)

- Use the web interface to send a message to the SQS queue.

![Screenshot (18)](https://github.com/user-attachments/assets/ec5ab9ab-3452-4583-8d40-8fb7f9a64329)

- Verify that the messages can be received from the queue:
  - Sent messages are stored in the SQS queue.
  - Receiving requests randomly fetch messages from the queue.
 
![Screenshot (19)](https://github.com/user-attachments/assets/8723ac33-5601-48bd-9309-ac83965d1897)

- Test by sending multiple messages and checking the queue for message consistency.
