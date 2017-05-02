

<!DOCTYPE html>
<html>
<head>
    <title>Zing-chart</title>
   
    <script src=" https://code.jquery.com/jquery-1.10.2.min.js"></script>
   
    <script src="https://cdn.zingchart.com/zingchart.min.js"></script>
   
    <script>
        var chart = {
            "type": "bar", /* Specify your chart type. eg. bar , bar3d ,  */
            "title": {
                "text": "ZingChart Bar"
            },
            "subtitle": {
                "text": "Default Style"
            },
            "height": "100%",
            "width": "85%",
            "x": "10%",
            "y": "0%",
            "series": [
            {
                "values": [11,26,7,44,11,28,42,26,13,8,6,15] , 
                "text": "Dogs",
                "offsetValues": [0, 3, 5, 15, 28, 30, 4, 9,1,3,5,2] /*offset effect*/
            },
            {
                "values": [13, 23, 14, 15, 16, 16, 27, 16, 13,10,20,25],
                "text": "Cats"
            },
            {
                "values": [22, 24, 16, 26, 25, 29, 24, 23, 28,10,15,26],
                "text": "Reptiles"
            },
            {
                "values": [31, 28, 34, 36, 28, 36, 39, 27, 36, 16, 26, 25],
                "text": "Birds"
            },
            {
                "values": [45, 38, 49, 42, 39, 48, 42, 40, 49, 36, 28, 36],
                "text": "Fish"
            },
            {
                "values": [50, 42, 57, 49, 53, 53, 48, 57, 53, 39, 48, 42],
                "text": "Horses"
            }
            ],
           
            "legend": {/*Legend properties*/
                "header": {
                    "text": "Header"
                },
                "footer":{
                    "text":"Footer"
                },
                "max-items":4,
                "overflow":"page",                
                "highlight-plot":true,
                "minimize":true,
                "draggable": true,
                "borderRadius": "3px" 
                
            },
            "plot": {
                "alpha": 0.9, /*opacity of plot*/
                "borderRadius": "2px", /*rounded corners*/
                "rules": [ /*applying conditions to plots*/
                       {
                       "rule": "%p === 4 && %i === 7", /*8th node of the 4th plot*/
                       "backgroundColor": "none",
                       "line-style": "dashed",
                       "border-color": "#447884",
                       "border-width": 1
                    },
                 {
                "rule": "%p === 3 && %i === 8", /*9th node of the 3rd plot*/
                "backgroundColor": "none",
                "line-style": "dashed",
                "border-color": "#ff9800",
                "border-width": 1
                 },
              ]
            },
            "scale-y": {/*y-axis settings*/
               
                "min-value": 0,
                "max-value": 100,
                "label": {/*y-axis title*/
                    "text": "Export count(%)",
                },
                //"format": "%v%", /*uncomment to see formating*/
            },
            "scale-x": {/*x-axis settings*/
                "values": ["January", "February", "March", "April", "May",
                           "June", "July", "August", "September",
                           "October", "November", "December"],
                "label": { /* x-axis Title */
                    "text": "Time",
                },
                "item": {
                    "font-angle": -45,/*providing angle to values*/
                    "max-chars": 3
                },
                "markers": [ /*Showing some portion with marker eg. in current chart red marker portion shown in graph*/
   	                 {
   	                  "type": "area",
   	                  "range": [1.5, 3.0],
   	                  "backgroundColor": "red",
   	                  "alpha": 0.2,
   	                  "label": {
   	                      "text": "Imp. Notification",
   	                      "angle": 0,
   	                      "offset-x": 10,
   	                      "offset-y": -260,
   	                      "color": "#7d7d7d",
                         
   	                  }
   	                  }
                ]
                
            },
            "tooltip": { /*tool tip settings*/
                "callout": true,
                "borderColor": "#F4F2F2",
                "borderWidth": 2,
                "borderRadius": "3px",
                
            },
            "arrows": [ /*showing an arow in plot*/
   	        
   	        {
   	       "backgroundColor": "red",
   	       "alpha": 0.7,
   	       "borderAlpha": 1,
   	       "from": {
   	          "hook": "node:plot=1,index=4" /*5th node of 1st plot*/
   	        },
   	       "to": {
   	          "hook": "node:plot=1,index=7" /*8th node of 1st plot*/
   	       },
   	      
   	       "offsetY": "-100px",
   	       "label": { /*lebel text for arrow*/
   	           "text": "Look Here",
   	           "bold": true,
   	           "backgroundColor": "none",
               "color":"black",
   	           "borderWidth": 0,
   	           "fontAngle": 0,
   	           //offsetX: -10,
   	           //offsetY: 8

   	       }
   	    }
             ],
        };
      
       var renderChart = function(data){
           zingchart.render({
               id: 'dashboard',
               output: "svg",
               data: data,

           });
        }
        $(document).ready(function () {

            renderChart(chart);
        });
    </script>

</head>
<body>

    <div id='dashboard' style="background-color:aliceblue"></div>
  
</body>
</html>
