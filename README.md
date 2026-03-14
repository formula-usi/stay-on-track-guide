# 🏁 Stay on Track @ Phänomena on Tour 2026

**Authors: Roberto Minelli & Samuele Pasini (Software Institute – USI, Lugano)**

This is the **short guide** for the daily operation of the Stay on Track installation at Phäenomena. The more extensive guide with everything you might need is available [here](https://github.com/formula-usi/stay-on-track-guide/blob/main/Full-Guide.md). **Before contacting us, please ensure that you've also read the full guide.**

## Beginning of the day
1. Turn on the beamer using its remote (Panasonic)
2. Turn on the touchscreen using its remote (Iiyama)
3. Turn on the display mounted on the side of the wooden structure that holds the beamer (Samsung)
4. Refer to the [full guide](https://github.com/formula-usi/stay-on-track-guide/blob/main/Full-Guide.md) if the screens are not configured correctly (e.g., you do not see the circuit projected on the floor, you do not see the circuit editor on the touchscreen display, you do not see the dashboard on the side mounted display)
5. Ensure that both laptops are connected to the power outlets (otherwise connect them)
6. Use the `formulausi` account with the password: `phaenomena2026!`
7. ⚠️ **Ensure that the circuit editor application (Path-ological) is running on Laptop #1**. If not, open a Terminal on Laptop #1 and run the following command:
```bash
pnpm run dev
```
7. Go to the next section and start a new car

## Starting a new car
1. Choose one of the cars, i.e., `piracer-x`
2. Turn it on using the `ON/OFF` button
3. Wait until the small on-board OLED display on the car turns on
4. Check if the battery is full (100%)
5. If so, put the car on the raised wooden floor
6. Otherwise, turn off the car, plug it in to charge, and choose a car with a fully charged battery
7. Connect Laptop #1 to a car, say `piracerpro-x` using the following command (the procedure is the same for all cars, replace the name with `piracerpro-1`, `piracerpro-2`, ...) :
``` bash
ssh piracerpro-x
```
8. Connect Laptop #2 to a car, say `piracerpro-x` using the following command (the procedure is the same for all cars, replace the name with` piracerpro-1`, `piracerpro-2`, ...) :
``` bash
ssh piracerpro-x
```
9. On Laptop #2 start the drive interface by running the followig command the Terminal:
```bash
python manage.py drive --model models/MODEL_NAME.pt
```
10. The `MODEL_NAME.pt` is the name of the location followed by the number of the car, for example in Dietikon for the car no. 3 (i.e., `piracerpro-3)` it will be `dietikon_3.pt`.
11. On Laptop #2, access the drive interface at [`localhost:8887/drive`](http://localhost:8887/drive).
12. Keep this interface on the screen of Laptop #2
13. On Laptop #2, access the cockpit at [`localhost:8887/cockpit`](http://localhost:8887/cockpit)
14. Move the cockpit on the display mounted on the side of the wooden structure that holds the beamer
15. On the drive interface set the `(M)ode` to `Full (A)uto`:

<img src="images/full_auto.jpg" alt="Full Auto Mode" width="400px"/>

16. Slowly move the `AI multiplier` (which is initially set to 0.00) to values close to 1.00. You might need to change this value after a few hours of operation, when the battery of the cars goes down (i.e., lower the battery, higher the multiplier).

<img src="images/multiplier.jpg" alt="AI Multiplier" width="400px"/>

17. ⚠️ **Ensure that Laptop #1 is connected to the car by changing the circuit or scenario** (i.e., surface and weather) on the touchscreen. Everytime a new circuit is projected on the floor, the car should do a small brake. If this doesn't happen, it means that Laptop #1 is not connected to the car. Please connect it as explained above.
18. In case you want to stop the car, move the `AI multiplier` to 0.00 or set the `(M)ode` to `(U)ser`

## Replacing a car
1. Close the Terminal connected to the car on Laptop #1 (Control Center). If prompted for confirmation, say yes. **Do not** close the Terminal running the circuit editor application. If you close it by mistake,  refer to the [full guide](https://github.com/formula-usi/stay-on-track-guide/blob/main/Full-Guide.md) to open this application again.
2. Close the Terminal connected to the car on Laptop #2 (Pit-stop). If prompted for confirmation, say yes.
3. Follow the steps explained above on how to start a new car

## End of the day

At the end of the day, you should follow this routine.

### Laptop #1 (Control Center)

1. Close the Terminal connected to the car on Laptop #1 (Control Center). If prompted for confirmation, say yes. **Do not** close the Terminal running the circuit editor application. If you close it by mistake,  refer to the [full guide](https://github.com/formula-usi/stay-on-track-guide/blob/main/Full-Guide.md) to open this application again.
2. Close the Terminal connected to the car on Laptop #2 (Pit-stop). If prompted for confirmation, say yes.
3. If `autoplay` is active, turn it off
4. Put the Laptop to sleep (without closing the lid)

We recommend to **leave all the screens connected** to facilitate the startup on the next day.

### Laptop #2 (Pit-stop)

1. Move the AI multipler to 0.00 on the drive interface (or put the car into `User` mode)
2. Close the Google Chrome page running the drive interface
3. Close the Google Chrome page running the cockpit interface
3. Stop the drive application by pressing `control+C` on the Terminal you used to run the driving script (`python manage.py drive --model models/MODEL_NAME.pt`).
4. Close this Terminal
4. Put the Laptop to sleep (without closing the lid)

### Screens
1. Put the beamer in standby using its remote
2. The touchscreen should automatically go in standby when you put the Laptop in standby (if not, turn it off with its remote)
3. Turn off the Samsung display mounted on the side of the wooden structure that holds the beamer

### Important
1. Remember to put all laptops in charge
2. Switch off all the cars
3. Put all cars in charge
