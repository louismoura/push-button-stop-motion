## Stop motion animation

Now that you have successfully taken individual photographs with your camera, it's time to try combining a series of still images to make a stop motion animation.

- **IMPORTANT** You must create a new folder to store your stills. In the terminal window, enter `mkdir animation`.

- Modify your code to add a loop to keep taking pictures every time the button is pressed:

    ```python
    camera.start_preview()
    frame = 1
    while True: 
        try:
            button.wait_for_press()
            camera.capture('/home/pi/animation/frame%03d.jpg' % frame)
            frame += 1
        except KeyboardInterrupt:
            camera.stop_preview()
            break
    ```

    *Because `while True` goes on forever, you have to be able to make it exit gracefully. Using `try` and `except` means it can deal with an exceptional circumstance - if you force it to stop with `Ctrl + C` it will close the camera preview and exit the loop*

    *`frame%03d` means the file will be saved as the name "frame" followed by a 3-digit number with leading zeroes - 001, 002, 003, etc. This allows them to be easily sorted into the correct order for the video.*

- Now set up your animation subject (e.g. LEGO), ready to start the stop motion animation.

- Press the button to capture the first frame, then rearrange the animation subject and press the button again to capture each subsequent frame.

- Once all the frames have been captured, press `Ctrl + C` to terminate the program.

- Open the `animation` folder in the file manager to see your stills collection.

