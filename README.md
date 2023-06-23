# Action Detection for Sign Language
---
This repository houses work that follows a tutorial presented on [YouTube](https://www.youtube.com/watch?v=doDUihpj6ro&t=4444s)
by Nicholas Renotte.

In its current state, the notebooks inside of this repository have been demonstrated to run in their full capacity as
of 23 June 2023.

Because the intended/target audience is probably less saavy, I will be descriptive regarding how to get this running.

In order to follow along, you will want to do the following:

1. Ensure that you have a `python 3.8` environment installed. For example:

```bash
conda create -n your_env_name python=3.8
```

2. Activate that conda environment:

```bash
conda activate your_env_name
```

3. Pip install the repository:

```bash
pip install -e .
```

4. Once this is done, you can run:

```bash
jupyter lab
```

Which will spin up a `jupyter lab` server on your local host, and from there, you should be off and running.

**NOTE**: If it doesn't work immediately, make sure your notebook is using the appropriate conda environment.
It should default to the currently active env.

**NOTES**:


## Some Notes on Notebook Execution
```python
cap = cv2.VideoCapture(0)
```

* This argument may need changed as it the integer values determines which video device to use.
* The code ran on a Windows machine (additional work need for WSL setups), and will likely run on Linux/Mac OS
* The following snippet of code (cell in a notebook), takes time to initialize and will open a video capture window.
  In order to stop capture, you must press the `q` key.

```python
cap = cv2.VideoCapture(0)
# Set mediapipe model 
with mp_holistic.Holistic(min_detection_confidence=0.5, min_tracking_confidence=0.5) as holistic:
    while cap.isOpened():

        # Read feed
        ret, frame = cap.read()

        # Make detections
        image, results = mediapipe_detection(frame, holistic)
        print(results)
        
        # Draw landmarks
        draw_styled_landmarks(image, results)

        # Show to screen
        cv2.imshow('OpenCV Feed', image)

        # Break gracefully
        if cv2.waitKey(10) & 0xFF == ord('q'):
            break
    cap.release()
    cv2.destroyAllWindows()
```