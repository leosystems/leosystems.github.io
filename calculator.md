---
title: Calculator
slug: calculator
lead: Compute several useful LEO parameters
icon: flask
---

<table>
    <tr>
        <td><label for="txtelangle">Elevation angle</label></td>
        <td><input type="text" id="txtelangle" /></td>
    </tr>
    <tr>
        <td><label for="txtHeight">Height from the surface (m)</label></td>
        <td><input type="text" id="txtHeight" /></td>
    </tr>
    <tr>
        <td></td>
        <td><button id="btnReset">Reset</button><button id="btnCalc">Calculate</button></td>
    </tr>
</table>
<br><br>
Central angle \\(\equiv\gamma= \arccos\left(\frac{R\_E}{R\_E+h}\cdot\cos(El)\right)-El=\\)
<m id="tdCentangle">
<m/>

<script type="text/javascript">
    window.onload=function() {
        elangleObj = document.getElementById('txtelangle');
        heightObj = document.getElementById('txtHeight');
        centangleObj = document.getElementById('tdCentangle');
        document.getElementById('btnReset').onclick = resetInputs;
        document.getElementById('btnCalc').onclick = calcOrbit;
    }
    function resetInputs() {
        elangleObj.value = '';
        heightObj.value = '';
        centangleObj.innerHTML = '';
    }
    function calcOrbit() {
        var elangle = new Number(elangleObj.value);
        var height = new Number(heightObj.value);
        centangleObj.innerHTML = '';
        if(isNaN(elangle) || isNaN(height)) {
            alert('Invalid elangle or height');
            return;
        }
        centangleObj.innerHTML = Math.acos((6370000/(6370000+height))*Math.cos(elangle))-elangle;
    }
</script>
