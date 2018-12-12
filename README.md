# AngularJS - Dropdown estados e cidades brasileiras
Elementos de seleção do HTML "\<select\>" com estados e cidades brasileiras com correlação, desenvolvido para AngularJS (1.x)

## Uso

Importar o módulo antes do script principal da aplicação
```html
<script src="br-location.js"></script>
<script src="app.js"></script>
```

Adicionar dependência no módulo e controller correspondente:
```javascript
// app.js
var app = angular.module('meuApp', ['brLocation']);
app.controller('myController', function($scope, brLocation) {
  $scope.brLocation = brLocation;
}
```

Componente de estados:
```html
<select ng-model="brLocation.estado" ng-change="brLocation.searchCitiesByState(brLocation.estado)">
  <option ng-repeat="estado in brLocation.data" value="{{estado.sigla}}">{{estado.nome}}</option>
</select>
```

Componente de cidades:
```html
<select ng-model="brLocation.cidade" name="city">		
  <option ng-repeat="cidade in brLocation.cidades" value="{{cidade}}">{{cidade}}</option>
</select>
```

Obter valores:
```javascript
$scope.brLocation.estado // Estado selecionado
$scope.brLocation.cidade // Cidade selecionada
```
