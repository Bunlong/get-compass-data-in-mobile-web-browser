## How to get compass data in mobile web browser

```html
<!DOCTYPE html>
<html>
  <body>
    <div id="display" />

    <script>
      if (window.DeviceOrientationEvent) {
        window.addEventListener('deviceorientation', event => {
          let compassdir;

          if (event.webkitCompassHeading) {
            // Safari browser
            compassdir = event.webkitCompassHeading;
          } else {
            compassdir = event.alpha;
          }

          // if (compassdir < 0) { compassdir += 360; }
          // if (compassdir > 360) { compassdir -= 360; }

          document.getElementById("display").innerHTML = compassdir;
        })
      } else {
        alert("Sorry, your browser doesn't support Device Orientation");
      }
    </script>
  </body>
</html>
```

## Reference

* [https://developers.google.com](https://developers.google.com/web/fundamentals/native-hardware/device-orientation?fbclid=IwAR3SWExp5zIz1_4Qyr3_fKeqIEEwDUNJIk0snh3e_MtzgHAWkBWS_hWPqC4)
* [https://www.sitepoint.com](https://www.sitepoint.com/using-device-orientation-html5/?fbclid=IwAR02oFkKkUaZS6a0wTZTicpgnEkaHJ9uu2HYWrhXF5fbkX_nP2eRFkaL-nY)
* [https://www.html5rocks.com](https://www.html5rocks.com/en/tutorials/device/orientation/index.html?fbclid=IwAR1fFf8brcVyR6PNJkMnSQVs7_Ftt5qLMhdp6Nxl_3qtsv98AxDTgGlH5W8)
