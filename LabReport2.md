# Lab Report 2

---------Part 1
 
 `ChatServer` Code: 
 ![Code](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-25%20at%205.00.39%20PM.png?raw=true)
 ![Code](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-25%20at%205.10.29%20PM.png?raw=true)

> * To write this code I used the lab2 setting with the code that my group made for lab2 "Make the Simplest “Search Engine”" part. This is the code that we had written with my group:
> ![GroupCode](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-26%20at%2012.39.23%20PM.png?raw=true)
> * Then I gave the above code to the copilot and asked to change it so it fits the lab requirements. And this was the code produced:
> ![Copilot Code](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-26%20at%2012.45.04%20PM.png?raw=true)
> * Afterwards, I changed the first return statement to fit the LabReport2 requirements better:
 ![ChangedReturn](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-26%20at%2012.48.02%20PM.png?raw=true)
> * However, the provided code would return Strings like "How are you" as "How+are+you+". So I asked ChatGpt to solve the issue in the code, and it modified this portion of the code:
 >![ChatGPTmoddified](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-26%20at%202.10.58%20PM.png?raw=true)

---
Output:
 ![Webscreenshot](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-25%20at%205.14.48%20PM.png?raw=true)
 * The `handleRequest` method is called when using `/add-message?s=Hello&user=Aru`.
 * The relevant argument to this method is the `URL`: `/add-message?s=Hello&user=Aru`. The `message` field is set to `Hello`, the `user` field is set to `Aru`, and the value of ArrayList `wr` is now `"Aru: Hello"`
 * The value of the ArrayList `wr` changed from `null` to `"Aru: Hello"` after the execution of the `handleRequest` method since the user and message parameters were extracted from the provided URL and formed a `chatMessage` which was added to the ArrayList `wr`.
   
 ![Webscreenshot](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-01-25%20at%205.15.48%20PM.png?raw=true)
 *  The `handleRequest` method is called when using `/add-message?s=How are you?&user=Aru`.
 
