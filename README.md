# add_display_modes.sh

## Description
This shell script adds multiple display modes with different refresh rates to the eDP-1 output using xrandr.

## Usage
1. Make sure the script is executable: `chmod +x add_display_modes.sh`
2. Run the script: `./add_display_modes.sh`

## Steps
1. Remove existing modes to avoid conflicts:
    ```sh
    xrandr --delmode eDP-1 "1920x1080_60.00"
    xrandr --rmmode "1920x1080_60.00"
    xrandr --delmode eDP-1 "1920x1080_75.00"
    xrandr --rmmode "1920x1080_75.00"
    xrandr --delmode eDP-1 "1920x1080_90.00"
    xrandr --rmmode "1920x1080_90.00"
    xrandr --delmode eDP-1 "1920x1080_100.00"
    xrandr --rmmode "1920x1080_100.00"
    xrandr --delmode eDP-1 "1920x1080_120.00"
    xrandr --rmmode "1920x1080_120.00"
    ```

2. Add new modes for different refresh rates:
   - **60Hz**:
     ```sh
     xrandr --newmode "1920x1080_60.00"  148.50  1920 2008 2052 2200  1080 1084 1089 1125 -hsync +vsync
     xrandr --addmode eDP-1 "1920x1080_60.00"
     ```
   - **75Hz**:
     ```sh
     xrandr --newmode "1920x1080_75.00"  220.75  1920 2056 2264 2608  1080 1083 1088 1120 -hsync +vsync
     xrandr --addmode eDP-1 "1920x1080_75.00"
     ```
   - **90Hz**:
     ```sh
     xrandr --newmode "1920x1080_90.00"  277.00  1920 2048 2248 2576  1080 1083 1088 1158 -hsync +vsync
     xrandr --addmode eDP-1 "1920x1080_90.00"
     ```
   - **100Hz**:
     ```sh
     xrandr --newmode "1920x1080_100.00"  285.50  1920 2040 2240 2560  1080 1083 1088 1120 -hsync +vsync
     xrandr --addmode eDP-1 "1920x1080_100.00"
     ```
   - **120Hz**:
     ```sh
     xrandr --newmode "1920x1080_120.00"  369.50  1920 2080 2288 2656  1080 1083 1088 1160 -hsync +vsync
     xrandr --addmode eDP-1 "1920x1080_120.00"
     ```

3. Set the desired mode sequentially:
    ```sh
    xrandr --output eDP-1 --mode "1920x1080_60.00"
    xrandr --output eDP-1 --mode "1920x1080_75.00"
    xrandr --output eDP-1 --mode "1920x1080_90.00"
    xrandr --output eDP-1 --mode "1920x1080_100.00"
    xrandr --output eDP-1 --mode "1920x1080_120.00"
    ```
