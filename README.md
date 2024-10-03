# Swagger-PetStore-API-Testing
This project contains automated tests for the Swagger PetStore API using Postman. The tests cover several API endpoints and verify the correctness of the responses by checking status codes, headers, and response data.

## API Details
- Base URL: https://petstore.swagger.io/v2
- Tested Endpoints:
GET /pet/findByStatus?status=pending

Additional queries can be run with different parameters, such as status=available, status=sold, etc.

## Postman Collection
The Postman collection contains the following requests:

- GET Find Pets by Status
- Test scripts included:
  
- Verify response code is 200.
- Check that the Content-Type is application/json.
- Ensure certain fields (photoUrls, tags, id, name, status, category) are present and valid.
  
## Postman Test Scripts
Here is an example of test scripts used in the collection:


console.log(pm.variables.get('baseUrl'))
pm.variables.set('thisIsADynamicVar', 'SampleValue')
console.log(pm.variables.get('thisIsADynamicVar'))
console.log(pm.response.json())
const bodyAsText = pm.response.text();

if (bodyAsText.toLocaleLowerCase().includes('pet')) {
    console.log('Body has the pet keyword');
} else {
    console.log('Body does not have the pet keyword')
}

pm.test("Response status code is 200", function () {
  pm.response.to.have.status(200);
});

Additional checks:

- photoUrls, tags, id, name, status, category fields validation.
  
## How to Run
1. ### Clone the repository:

git clone <repository-url>

2. ### Import the Postman collection:
   
- Open Postman, go to Import > Upload Files, and select the exported JSON file from the collections folder.
  
3. ### Run the collection:
- You can use the Collection Runner or run individual requests manually.
  
## License
This repository is licensed under the MIT License.

## Disclaimer
Please note that the app/API tested in this project is the property of SoftUni, and this repository only contains my personal testing and automation scripts related to it.
