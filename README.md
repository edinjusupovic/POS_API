# Point of Sales API 

A simple API built with NodeJS designed for a backend customer invoice system with MongoDB. 

## Getting Started

### Prerequisites

* NodeJS 
* MongoDB
* MongooseJS 
* ExpressJS 

Everything else is covered in the npm included with this project. 

### Installation 

Do 'npm install' and then run app.js from the main directory. 

## API usage 

Listed below are the API codes. 

Send a new invoice to be created (HTTP POST):
```
{
	"name": "John Smith", 
	"address": "742 Evergreen Terrace", 
	"services": "foo bar",
	"balanceTotal": "49.95"
}
```

Invoice created and added to the database succesfully:
```
{
  "status": {
    "message": "invoice_creation_success"
  }
}
```

### Errors

One or more fields on the invoice are missing, invoice not created nor
added to the database: 
```
{
  "status": {
    "message": "invoice_creation_missing-data"
  }
}
```

The balance property sent is returning an error, check to ensure it meets
the parameters and note the invoice has not been added to the database: 
```
{
  "status": {
    "message": "invoice_creation_balance-error"
  }
}
```