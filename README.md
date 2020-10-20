# Self-driving-car-in-GTAV
Data collecting, training and testing autopilot in video game.

In order to use this following programs are required:
- GTAV with extended camera mod (camera on hood of a car),
- Cheat engine,
- vjoy SDK

How to use:

1. Run Cheat engine and find car speed value in memory. After finding speed address, open cheat table LUA script (in Cheat engine) and copy paste gtaV_helper content there with changed adres in 4th row to match current speed address, then execute the script,

2. Run SelfDrivingAIDataColecting.ipynb Main loop cell (after loading dependencies and data) to collect screen, speed and Joystick input. Press T to toggle pause/unpause data streaming.

3. Run training_model.ipynb to train model. I did this in google colab because of GPU limitations (also copied training data to google drive),

4. In order to test model use SelfDrivingModelTesting(grabScreen).ipynb (if used google colab copy model from google drive to local machine)

Conclusion:

In order to make good model huge amount of data is requered. Even after 2-3 hours of data collecting AI falls into situation where he doesn't know what to do pretty fast (e.g. if he comes close to building and can't see the road). Reading input from steering wheel would be more precise, however setting it up is harder then joystick. In the end training model to drive in the video game is better to do with RNN (if controlled video game environment is available).


