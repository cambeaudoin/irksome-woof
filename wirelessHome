<html>

<head>
    <META NAME="WT.ti" CONTENT="Wireless">
    <META NAME="WT.sp" CONTENT="en">
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>Wireless Support</title>
    <style type="text/css">
        body {
            overflow-x: hidden;
        }
    </style>
</head>

<body>

    <?php
    //this fuction creates a table for every product in the series
function Series($anchor, $title) {
	echo '<div class="NewTable"><table><thead>';
    //$anchor is the actual HTML anchor. This is how you can quickly navigate to a page section.
    //$title is the name of the section that becomes a header
	echo '<th colspan="4"><a name="' . $anchor . '"></a>' . $title;
	echo '<hr />';
	echo '</th></thead><tbody>';
}

function OpenCSV($filename) { 
    //with this, we actually open and read a CSV file that has 3 pieces of information. Ex:EOS 70D,6D_sm.png,845 (product name, image name, RNW ID)
$a = array();
$x = 0;
$f = fopen("http://www.canon.ca/support_images/wifits/data/$filename.csv", 'r'); //filename taken from the argument above
while ($line = fgetcsv($f)) //$line is the array
	{
		$a[$x] = $line; //assign key to new array
		$x++;
	}
sort($a); //sort the main array by key
fclose($f);

echo '<tr>';
$x=0;
	foreach ($a as $inner) { // Enter first level of array
		if (is_array($inner)){ // Enter inner array
			echo '<td width="233" align="center">';
			echo '<a class="product_link" href="http://canoncanada.custhelp.com/app/answers/list/st/5/c/938/p/' . $inner[2]; //set link destination
			echo '"><img src="http://www.canon.ca/support_images/wifits/data/PNG_SM/' . $inner[1]; //set image for product
						//Remember that all images must go on the FTP server at the above location
			echo '" alt="' . $inner[0];
			echo '" width="120" /><br />' . $inner[0] . '</a></td>';
			$x++;
			if ($x > 3) { //New row after $x cells. make sure you match this below as well (colspan in Series function)
				echo '</tr>';
				echo '<tr>';
				$x = 0;
			}
		}
	}
	echo '</tbody></table></div>';
}
?>
        <!-- okay okay, I know it's not responsive, but it's supposed to fit into a very specific iframe. There's no reason to add complexity when you know the parent site is not responsive either -->

        <div class="minorLinks">
            <a href="#MG">PIXMA MG Series</a> |
            <a href="#MP">PIXMA MP Series</a> |
            <a href="#MX">PIXMA MX Series</a> |
            <a href="#SELPHY">SELPHY Series</a> |
            <a href="#imageCLASS">imageCLASS Series</a> |
            <a href="#Pro">PIXMA Pro Series</a> |
            <a href="#MAX">MAXIFY Series</a> |
            <a href="#IPIX">PIXMA iP &amp; iX Series</a>
            <br />
            <a href="#EOS">Digital EOS</a> |
            <a href="#PS">PowerShot</a>
            <br />
            <a href="#HF">VIXIA HF Camcorders</a> |
            <a href="#MINI">VIXIA mini Camcorders</a> |
            <a href="#HD">High Definition Camcorders</a>
        </div>

        <?php 
//Home Printers
Series("MG","PIXMA MG Series");
OpenCSV(PixmaMG_EN);

Series("MP","PIXMA MP Series");
OpenCSV(PixmaMP_EN); 

Series("MX","PIXMA MX Series");
OpenCSV(PixmaMX_EN); 

Series("SELPHY","SELPHY Series");
OpenCSV(Selphy_EN);


//Office&Pro Printers
Series("imageCLASS","imageCLASS Printer Series");
OpenCSV(imageCLASS_EN);

Series("Pro","PIXMA Pro Series");
OpenCSV(PixmaPro_EN);

Series("MAX","MAXIFY Series");
OpenCSV(MAXIFY_EN);

Series("IPIX","PIXMA iP & iX Series");
OpenCSV(PixmaiPiX_EN);


//Cameras
Series("EOS","EOS Cameras");
OpenCSV(EOS_EN);

Series("PS","PowerShot Cameras");
OpenCSV(PS_EN);


//Camcorders
Series("HF","VIXIA HF Camcorder Series");
OpenCSV(VixiaHF_EN);

Series("MINI","VIXIA mini Camcorder Series");
OpenCSV(VixiaMINI_EN);

Series("HD","High Definition Camcorders");
OpenCSV(HD_EN);
?>

            </table>
            </div>
</body>
</html>
