import pyautogui
import random
import time
import math

# Simulated screen resolution
SCREEN_WIDTH, SCREEN_HEIGHT = 1920, 1080
CROSSHAIR_POS = (SCREEN_WIDTH // 2, SCREEN_HEIGHT // 2)

# Simulated enemy detection (random location near center)
def detect_enemy():
    offset_x = random.randint(-300, 300)
    offset_y = random.randint(-200, 200)
    return (CROSSHAIR_POS[0] + offset_x, CROSSHAIR_POS[1] + offset_y)

# Smooth aim movement
def smooth_aim(current_pos, target_pos, speed=0.2):
    dx = target_pos[0] - current_pos[0]
    dy = target_pos[1] - current_pos[1]
    distance = math.hypot(dx, dy)
    steps = int(distance / 10)
    for i in range(steps):
        step_x = current_pos[0] + dx * (i / steps)
        step_y = current_pos[1] + dy * (i / steps)
        pyautogui.moveTo(step_x, step_y, duration=speed / steps)

# Main simulation loop
def aim_assist_sim():
    print("Scanning for targets...")
    time.sleep(1)

    enemy_pos = detect_enemy()
    print(f"Enemy detected at {enemy_pos}")

    print("Engaging target...")
    smooth_aim(CROSSHAIR_POS, enemy_pos)
    pyautogui.click()
    print("Fired at target!")

# Run the simulator
aim_assist_sim()
