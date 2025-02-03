# IntegrationPostmanTest

Buenas Noches Ing. Jose Miguel
a continuacion describo los casos de Test :
Direccion Local de la API tipo Get : https://localhost:7187/api/Servicio
se realizaron 5 Test al codigo, 4 correctas y 1 incorrecta a continuacion el codigo aplicado :


pm.test("Status code is 200", () => {
  pm.expect(pm.response.code).to.eql(200);
});

pm.test("Name Service is Catering", () => {
  const responseJson = pm.response.json();
  pm.expect(responseJson[0].nombre).to.eql("Catering");
});

pm.test("Cost Service Catering is Correct", () => {
  const responseJson = pm.response.json();
  pm.expect(responseJson[0].costo).to.eql(300);
});

const jsonData = pm.response.json();
pm.test("Test data type of the response", () => {
  pm.expect(jsonData[0]).to.be.an("object");
  pm.expect(jsonData[0].nombre).to.be.a("string");
    pm.expect(jsonData[0].descripcion).to.be.a("string");
  pm.expect(jsonData[0].costo).to.be.a("number");
});

const json = pm.response.json();
pm.test("Value is in valid list", () => {
  pm.expect(json[0].nombre)
    .to.be.oneOf(["Delivery", "Asesoramiento Nutricional"]);
});


<img width="950" alt="image" src="https://github.com/user-attachments/assets/c24cebf3-e7ca-42bf-a3c0-2dcbcf71e6ed" />

