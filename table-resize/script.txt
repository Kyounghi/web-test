// Code goes here

var app = angular.module('myApp', []);

app.controller('myCtrl', function($scope) {
  $scope.files = [
    {
      id: 1,
      name: 'One'
    }, {
      id: 2,
      name: 'Two'
    }
  ];
  
  $( "#selectable" ).selectable({
    filter: '.file',
    stop: function() {
        $( ".file", this ).each(function(i, file) {
          if ($(file).hasClass('ui-selected')) {
            $scope.files[i]._selected = true;
          } else {
            $scope.files[i]._selected = false;
          }
        });
        $scope.$apply();
      }
  });

  $('table.resizable').resizableColumns();

})

;