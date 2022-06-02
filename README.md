# Generate graph of type "TYPE"

Add the following lines of code

#### In your controller

```PHP
use Gebrail\ChartsReports\ChartReport;

// ...

$nombre_del_parametro = the sql query->get();

 $options = [
    'chart_name' => 'nombre_de_la_grafica',
    'chart_type' => 'tipo_de_grafica',
    'chart_subtype' => 'sub_tipo_de_grafica',
    'categoryXField' => 'nombre_del_campo_para_el_eje_X',
    'categoryYField' => 'nombre_del_campo_para_el_eje_Y',
    'chart_time' => 'day',
    'chart_data'=> $nombre_del_parametro,
           ];
$chart = new ChartReport($options);

return view('myview', compact('chart'));

```

#### In your View

```HTML
<!doctype html>
<html lang="en">
  <head>
{!! $chart->renderChartLibrary() !!}
{!! $chart->renderJs() !!}
  </head>
  <body>
   {!! $chart->renderHtml() !!}
    </body>
</html>

```

#### The result should be similar to the following image

![Imagen de prueba](https://www.amcharts.com/wp-content/uploads/2013/11/demo_129_none-1-1024x690.png "Estamos en fase beta")
