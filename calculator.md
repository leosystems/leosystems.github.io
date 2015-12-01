---
title: Calculator
slug: calculator
lead: Compute several useful LEO parameters
icon: flask
---

<style>
#Xpos,#Ypos,#Angle, #ElAngle {
    font-size: 16px;
    color: red;
}
.curve{
  width:900px; height:600px;
  border:solid 5px #000;
  background-image: url("/assets/img/bg.jpg");
  background-repeat: no-repeat;
  border-color:#000 transparent transparent transparent;
  border-radius: 40%/5px 5px 0 0;
}
</style>

<!-- CSS -->
<style type="text/css">
.drag {
    width: 180px;
    height: 110px;
    background-image: url("/assets/img/css-satellite.png");
    background-repeat: no-repeat;
    cursor: pointer;
    border-radius: 10px;
    text-align: center;
}
</style>

<table>
    <tr>
        <td><label for="txtelangle">Elevation angle* (degrees)</label></td>
        <td><input type="text" id="txtelangle" /></td>
    </tr>
    <tr>
        <td><label for="txtHeight">Height from the surface (km) </label></td>
        <td><input type="text" id="txtHeight" /></td>
    </tr>
    <tr>
        <td></td>
        <td><button id="btnReset">Reset</button><button id="btnCalc">Calculate</button></td>
    </tr>
</table>
<br>
<div>
<p>
* Note that an angle \\(\theta > 180\\)º doesn't have any physical meaning.
</p>
<p>
Central angle (º) \\(\displaystyle\equiv\gamma= \arccos\left(\frac{R\_E}{R\_E+h}\cdot\cos(El)\right)-El=\\)
<span id="tdCentangle"><span/>
</p>
<p>
Linear speed (m/s) \\(\displaystyle\equiv\sqrt{\frac{k}{R\_E+h}}=\\)
<span id="tdLinearSpeed"><span/>
</p>
<p>
Angular speed (rad/s) \\(\displaystyle\equiv\omega\_s=\frac{\nu\_s}{(R\_E+h)}=\sqrt{\frac{k}{(R\_E+h)^3}}=\\)
<span id="tdAngularSpeed"><span/>
</p>
<p>
Orbital period (s) \\(\displaystyle\equiv 2\pi\sqrt{\frac{(R\_E+h)^3}{k}}=\\)
<span id="tdOrbitalPeriod"><span/>
</p>
<p>
Distance to the edge (m) \\(\displaystyle\equiv\sqrt{R\_E^2+(R\_E+h)^2-2R\_E(R\_E+h)\cos\gamma }=\\)
<span id="tdDistanceEdge"><span/>
</p>
<p>
Area of the spherical cap (m\\(^2\\)) \\(\displaystyle\equiv S=2\pi R\_E^2(1-\cos\gamma)=\\)
<span id="tdSphericalCap"><span/>
</p>
<p>
Minimum number of satellites \\(\displaystyle\equiv\frac{4\pi R\_E^2}{S}=\frac{2}{1-\cos\gamma}=\\)
<span id="tdNumberSat"><span/>
</p>
<p>
With \\(k\\) being the Kepler's constant as in <A href="/#kepler">here</a>
</p>
</div>
<p>
<div id="box" class="curve">
        <div id="dragx" class="drag">
        <p id="Ypos"><p>
        <p id="Angle"><p>
        <p id="ElAngle"><p>
        </ul>
        </div>
</div>
</p>

<script type="text/javascript">

$(function () {
  $("#dragx").css({top: 1300, left: 550, position:'absolute'});
        $("#dragx").draggable({
                containment: "#box",
                scroll: false,
                drag: function(){
                    var offset = $(this).offset();
                    var x = offset.left;
                    var y = offset.top;
                    var xPos = (offset.left-550)*1.2;
                    var yPos = (-offset.top+2500)*1.2;
                    var radEarth = 6370000;
                    var elangle = Math.atan(yPos/xPos);
                    var degelangle = Math.abs(180/Math.PI*elangle);
                    var angle = 180/Math.PI*(Math.acos((radEarth/(radEarth+yPos)*Math.cos(elangle)))-elangle);
                    $('#ElAngle').text('Elevation angle: ' + degelangle+ 'º');
                    $('#Angle').text('Central angle: ' + angle+'º');
                    $('#Ypos').text('Height: ' + yPos+' km');
                },
        });
});

    window.onload=function() {
        elangleObj = document.getElementById('txtelangle');
        heightObj = document.getElementById('txtHeight');
        centangleObj = document.getElementById('tdCentangle');
        linearSpeed = document.getElementById('tdLinearSpeed');
        angularSpeed = document.getElementById('tdAngularSpeed');
        distanceEdge = document.getElementById('tdDistanceEdge');
        orbitalPeriod = document.getElementById('tdOrbitalPeriod');
        sphericalCap = document.getElementById('tdSphericalCap');
        numberSat = document.getElementById('tdNumberSat');
        document.getElementById('btnReset').onclick = resetInputs;
        document.getElementById('btnCalc').onclick = calcParameters;
    }
    function resetInputs() {
        elangleObj.value = '';
        heightObj.value = '';
        linearSpeed.innerHTML = '';
        angularSpeed.innerHTML = '';
        distanceEdge.innerHTML = '';
        orbitalPeriod.innerHTML = '';
        sphericalCap.innerHTML = '';
        numberSat.innerHTML = '';
        centangleObj.innerHTML = '';
    }
    function toRadians (angle) {
      return angle * (Math.PI / 180);
    }
    function toDegrees (angle) {
      return angle * (180 / Math.PI);
    }
    function calcParameters() {
        var radEarth = 6371000;
        var k = 3.9860e14;
        var elangle = new Number(elangleObj.value);
        var heightKm = new Number(heightObj.value);
        var height = heightKm*1000;
        centangleObj.innerHTML = '';
        linearSpeed.innerHTML = '';
        angularSpeed.innerHTML = '';
        distanceEdge.innerHTML = '';
        orbitalPeriod.innerHTML = '';
        sphericalCap.innerHTML = '';
        numberSat.innerHTML = '';

        if(isNaN(elangle) || isNaN(height)) {
            alert('Invalid parameters. Try with a positive length or an angle lower than 180º');
            return;
        }
        while(elangle > 360){
            elangle = elangle-360;
        }
        if(180 < elangle && elangle < 360){
          elangle = elangle-180;
        }
        if(90 < elangle && elangle < 180){
          elangle = 180-elangle;
        }

        var radelangle = toRadians(elangle);

        centangleObj.innerHTML = 180/Math.PI*(Math.acos((radEarth/(radEarth+height)*Math.cos(radelangle)))-radelangle);
        var centAng = Math.acos((radEarth/(radEarth+height)*Math.cos(radelangle)))-radelangle;
        linearSpeed.innerHTML = Math.sqrt(k/(radEarth+height));
        angularSpeed.innerHTML = Math.sqrt(k/((radEarth+height)*(radEarth+height)*(radEarth+height)));
        orbitalPeriod.innerHTML = 2*Math.PI*Math.sqrt((Math.pow((radEarth+height),3)/k));
        distanceEdge.innerHTML =  Math.sqrt((radEarth*radEarth)+((radEarth+height)*(radEarth+height))-2*radEarth*(radEarth+height)*Math.cos(centAng));
        sphericalCap.innerHTML = 2*Math.PI*radEarth*radEarth*(1 - Math.cos(centAng));
        numberSat.innerHTML = 2/(1-Math.cos(centAng));
    }
</script>
