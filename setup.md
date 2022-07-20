# Setup
Depending from where you got the game, go to the correct directory.   

   MS Store Version: `%LOCALAPPDATA%\Packages\Microsoft.254428597CFE2_8wekyb3d8bbwe\LocalCache\Local\HaloInfinite\Settings`

   Steam Version: `%LOCALAPPDATA%\HaloInfinite\Settings`

1. Ensure V-Sync is disabled and your Maximum FPS is set to unlocked ingame.

2. Open `SpecControlSettings.json`.

3. Go to this section:
   ```json
    "spec_control_minimum_framerate": {
        "version": 2,
        "value": 0
    },
    "spec_control_target_framerate": {
        "version": 1,
        "value": 960
    }    
    ```
    Change the value of  `"spec_control_minimum_framerate"` to `960`. The game will automatically set this back to 960. 

   ```json
    "spec_control_minimum_framerate": {
        "version": 2,
        "value": 960
    },
    "spec_control_target_framerate": {
        "version": 1,
        "value": 960
    }    
    ```
4. Save the file.

## How does setting my minimum framerate to `960` improve performance?

The minimum framerate option does 2 things:

1. Dynamically changes the render resolution to ensure the game hits the specified minimum framerate.
2. Respects your selected render resolution scale and doesn't deviate to far from it.              
    Essentially tries to ensure to keep your selected render resolution while trying to dynamically adjust the render resolution.

By setting the minimum framerate to `960`, we are telling the engine to maintain `960` fps but under real circumstances this is not possible which in turn results in Dynamic Resolution Scaling aka DRS to act very aggressively which in turn improves framerates.  

If you want more insight on how DRS or minimum framerate affects performance;          
Check out [`Minimum Frame Halo Infinite`](https://github.com/Aetopia/Minimum-Framerate-Halo-Infinite).