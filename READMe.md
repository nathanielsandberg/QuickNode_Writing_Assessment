# Transactions API

You can use APIs to do the following:  

* Get data.  
* Add new data.  
* Delete data when you no longer need it.  

With an API, multiple systems can interact with the same information to keep a centralized record of your data.
Your systems can be interoperable and exist in many different code bases when you use APIs.
You can make changes on the front-end that don't require changes on the backend, and you can make changes to the backend and the API that don't require changes on the front-end.  

You should learn how to do the following in this document:  

* Download the repository.
* Start the application.  
* Get the current transactions.
* Add a transaction to the transactions array.
* Delete a transaction from the transactions array.

## Prerequisites

You should do the following to complete this tutorial:  

* Download [Node.js](https://nodejs.org/en/download/).  
    **Note:** Download the latest long time support or LTS version for the most stability.  
* Download [Git](https://git-scm.com/downloads) or the command line tool of your choice.
* Download [curl](https://curl.se/download.html) for your system.

## Downloading the Repository and Starting the Application

1. In the folder of your choice, clone the repository.  
    On the command line, type the following:  

    ```bash
    git clone https://github.com/quiknode-labs/DocumenationWriterInterview.git
    ```

1. Change directories to get to the project.  
    On the command line, type the following:  

    ```bash
    cd DocumenationWriterInterview/Written
    ```

1. Change the import statement in `index.js` to a constant.  
    In the `index.js` file, change `import express from "express";` to `const express = require('express');`.

1. Start the application.  
    On the command line, type the following:  

    ```bash
    node index.js
    ```

You should see the following when the application is running:  

```bash
Example app listening at http://localhost:3000
```

## Getting Your Transactions

You need to get your current transactions.
Open another command line in any folder and type the following:  

```curl
curl localhost:3000
```

You should see a list of the transactions that the application starts with:  

```curl
[
  {
    "id": 1,
    "amount": 25,
    "to": "joe"
  }
]
```

## Adding Transactions

You may also need to add transactions to your list of transactions.  
On the command line, type the following and replace the values with a value of your choice to add to your list of transactions:

```curl
curl --location --request POST 'localhost:3000' --header 'Content-Type: application/json' --data-raw '{
    "id": {yourID},
    "amount": {yourAmount},
    "to": "{someName}"
}'
```

You should get the following response:  

```curl
successfully added transaction #: {yourID}, in the amount of {yourAmount} to: {someName}
```

**Note:** You can only use numbers and decimals for the `id` and the `amount`.  

You can now get your transactions to see your new transaction added to the list of transactions.

## Removing Transactions

You may also need to remove a transaction from your transactions when you have finished processing it.
On the command line that you have opened, type the following to delete the transaction:

```curl
curl --location --request DELETE 'localhost:3000' --header 'Content-Type: application/json' --data-raw '{
    "id": {yourIDToDelete},
    "amount": {yourAmountToDelete},
    "to": "{yourNameToDelete}"
}'
```

You should see the following response:  

```curl

```

## Next Steps

You should have learned how to do the following from this document:  

* Download the repository.
* Start the application.  
* Get the current transactions.
* Add a transaction to the transactions array.
* Delete a transaction from the transactions array.

You can now use the example code to work with your API locally or deploy the code to a server to create a public API.
You may want to secure your API with some authorization before making it public.
You can now have multiple systems use one API as the single source of truth to give your interoperability and to make your information easier to maintain.  
