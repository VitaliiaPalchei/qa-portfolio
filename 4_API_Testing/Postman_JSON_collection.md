[dummyjson-api-collection.json .json](https://github.com/user-attachments/files/24403206/dummyjson-api-collection.json.json)
{
	"info": {
		"_postman_id": "8129d333-c5a6-48a3-b74a-c8feac5d028c",
		"name": "DummyJSON_testing",
		"description": "API testing project for DemoWebShop web app. Includes user registration, login, product catalog, and cart management. Cover positive and negative scenarios.",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
		"_exporter_id": "18271907"
	},
	"item": [
		{
			"name": "TC01_Register_user_Sucsses",
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\n  \"email\": \"{{user_email}}\",\n  \"password\": \"{{user_password}}\",\n  \"firstName\": \"Maria\",\n  \"lastName\": \"Povale\"\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "{{base_url}}/users/add",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"users",
						"add"
					]
				}
			},
			"response": []
		},
		{
			"name": "TC02_Register_Missing_Email_Negative",
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\n  \"email\": \"\",\n  \"password\": \"{{user_password}}\",\n  \"firstName\": \"Vita\",\n  \"lastName\": \"Povale\"\n}\n",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "{{base_url}}/users/add",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"users",
						"add"
					]
				}
			},
			"response": []
		},
		{
			"name": "TC03_Login_Valid",
			"event": [
				{
					"listen": "prerequest",
					"script": {
						"exec": [
							"pm.test(\"Login successful\", function () {",
							"    pm.response.to.have.status(200);",
							"    var jsonData = pm.response.json();",
							"    pm.environment.set(\"auth_token\", jsonData.token);",
							"});",
							""
						],
						"type": "text/javascript",
						"packages": {}
					}
				}
			],
			"protocolProfileBehavior": {
				"disabledSystemHeaders": {}
			},
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\n  \"username\": \"emilys\",\n  \"password\": \"emilyspass\",\n  \"expiresInMins\": 30\n}\n\n\n\n",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "{{base_url}}/auth/login",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"auth",
						"login"
					]
				}
			},
			"response": []
		},
		{
			"name": "TC04_Login_Invalid_Password",
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\n  \"username\": \"emilys\",\n  \"password\": \"wrong_password\"\n}\n\n",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "{{base_url}}/auth/login",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"auth",
						"login"
					]
				}
			},
			"response": []
		},
		{
			"name": "TC05_Get_product_List",
			"event": [
				{
					"listen": "prerequest",
					"script": {
						"exec": [
							"pm.test(\"Status code is 200\", function () {",
							"    pm.response.to.have.status(200);",
							"});",
							"",
							"pm.test(\"Response contains array of products\", function () {",
							"    var jsonData = pm.response.json();",
							"    pm.expect(jsonData.length).to.be.above(0);",
							"});",
							""
						],
						"type": "text/javascript",
						"packages": {}
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "{{base_url}}/products",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"products"
					]
				}
			},
			"response": []
		},
		{
			"name": "TC06_Get_product_by_ID",
			"event": [
				{
					"listen": "prerequest",
					"script": {
						"exec": [
							"pm.test(\"Status code is 404\", function () {",
							"    pm.response.to.have.status(404);",
							"});",
							"",
							"pm.test(\"Response contains error message\", function () {",
							"    var jsonData = pm.response.json();",
							"    pm.expect(jsonData.error).to.eql(\"Product not found\");",
							"});",
							""
						],
						"type": "text/javascript",
						"packages": {},
						"requests": {}
					}
				}
			],
			"protocolProfileBehavior": {
				"disableBodyPruning": true
			},
			"request": {
				"method": "GET",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "{{base_url}}/products/7",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"products",
						"7"
					]
				}
			},
			"response": []
		},
		{
			"name": "TC07_Add_Product_to_Cart",
			"event": [
				{
					"listen": "prerequest",
					"script": {
						"exec": [
							"",
							""
						],
						"type": "text/javascript",
						"packages": {},
						"requests": {}
					}
				},
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 200\", function () {",
							"    pm.response.to.have.status(200);",
							"});",
							"",
							"pm.test(\"Cart ID is returned\", function () {",
							"    const jsonData = pm.response.json();",
							"    pm.expect(jsonData.id).to.be.a(\"number\");",
							"});",
							"",
							"pm.test(\"Cart contains products\", function () {",
							"    const jsonData = pm.response.json();",
							"    pm.expect(jsonData.products).to.be.an(\"array\");",
							"    pm.expect(jsonData.products.length).to.be.above(0);",
							"});",
							"",
							"pm.test(\"Total quantity is greater than 0\", function () {",
							"    const jsonData = pm.response.json();",
							"    pm.expect(jsonData.totalQuantity).to.be.above(0);",
							"});",
							"",
							"// Save cart_id for delete request",
							"pm.environment.set(\"cart_id\", pm.response.json().id);",
							""
						],
						"type": "text/javascript",
						"packages": {},
						"requests": {}
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\n  \"userId\": 1,\n  \"products\": [\n    {\n      \"id\": 1,\n      \"quantity\": 1\n    }\n  ]\n}\n",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "{{base_url}}/carts/add",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"carts",
						"add"
					]
				}
			},
			"response": []
		},
		{
			"name": "TC08_Delete_Cart",
			"event": [
				{
					"listen": "prerequest",
					"script": {
						"exec": [
							""
						],
						"type": "text/javascript",
						"packages": {},
						"requests": {}
					}
				},
				{
					"listen": "test",
					"script": {
						"exec": [
							""
						],
						"type": "text/javascript",
						"packages": {},
						"requests": {}
					}
				}
			],
			"request": {
				"method": "DELETE",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\n  \"productId\": 999999,\n  \"quantity\": 1\n}\n",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "{{base_url}}/carts/{{cart_id}}",
					"host": [
						"{{base_url}}"
					],
					"path": [
						"carts",
						"{{cart_id}}"
					]
				}
			},
			"response": []
		}
	]
}
