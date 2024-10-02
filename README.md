# Neuroscience Laboratory  
**Assignment 2: Psychtoolbox NeuroLab Course - Visual Search**

## Overview

This assignment focuses on visual search tasks, inspired by the role of reward history in primate object recognition. It simulates the rapid differentiation of objects based on their reward values, testing how training duration affects search efficiency for high-value objects amidst distractors.

### Background
Survival for most animals relies on quickly identifying rewarding objects. Searching for a single target surrounded by distractors is often difficult and time-consuming. However, research by Hikosaka et al. (2014) suggests that primates can robustly and rapidly differentiate objects based on their reward history. We hypothesize that this robust coding supports an efficient "pop-out" search mechanism for high-value objects.

To test this hypothesis, subjects view a series of complex objects with biased rewards over varying training periods (1, 5, or 30 days). After training, they search for high-value objects (Good) among distractors (Bad) in both target-present and target-absent trials (Ghazizadeh et al., 2016).

---

## Experiment Structure

### Search Task
- **Target Present (TP)**: A single Good object among Bad distractors.
- **Target Absent (TA)**: All objects are Bad.

Subjects undergo four sessions with equal TP and TA trials for each Good fractal. Sessions last about 12 minutes with 144 trials in total, split equally between perceptual and value groups.

### Experiment Settings:
- **Total Objects**: 48 fractals
  - **Value Group**:
    - 12 Good
    - 12 Bad
  - **Perceptual Group**:
    - 12 Good
    - 12 Bad
- **Sessions**:
  - 4 sessions per subject
  - Equal TP and TA trials
  - Each session lasts ~12 minutes
- **Trial Structure**:
  1. Fixation at the center
  2. Fixation disappears, objects appear
  3. Subject selects an object or rejects the trial by pressing a key
  4. Reward delivery based on group (Value or Perceptual) and object type (Good or Bad)

### Search Steps:
1. **Fixation Point**: Center fixation followed by object onset.
2. **Object Selection or Rejection**:
   - **Select**: Fixate on the object and press the space button.
   - **Reject**: Press the X button.
3. **Display Off**: End of trial with reward delivery.

### Display Size (DS):
Objects are presented with 3, 5, 7, or 9 objects in random assignment. Rotation of objects is randomly set between 1-360°.

---

## Trial Phases:
1. **Fixation**: 300-500 ms, followed by object onset (up to 3 seconds).
2. **No Press**: Results in an error beep with a 1.5s inter-trial interval (ITI).
3. **Reject Press (TA)**: After 2-4 random correct rejections, low reward is delivered.
4. **Reject Press (TP)**: Same as TA but without reward.
5. **Accept Press**: Reward or error beep based on fractal selection.

---

## Tasks

### 1. **State Diagram**  
Draw a state diagram representing all states and conditions of the visual search task.

### 2. **Fractal Assignment**  
Randomly assign fractals across four categories (Value/Perceptual, Good/Bad) to control biases. Ensure equal appearances for each fractal across trials and subjects. Calculate how many subjects are needed for equal appearance.

### 3. **Trial Implementation**  
Implement the search phase as described. Each trial should have fractals placed randomly based on conditions (TA/TP, Value/Perceptual, DS). Ensure equal appearances of each fractal in the 144 trials.

### 4. **Simulation of Search Phase**  
- Collect subject ID and session number at the beginning.
- Simulate eye movement using mouse position and key presses for decisions.
- Display green (Good) and red (Bad) rectangles for fractal selection.
- Record a video of the search task, including various conditions (No press, Reject press, Accept press, etc.).

### 5. **Information Box**  
Display an information box in the corner of the recorded video with key details (e.g., key pressed, group type, reward amount).

### 6. **Output Data**  
Save output data to a `.mat` file, including:
  - Subject ID, session number, fractal size, peripheral circle degree, screen size
  - For each trial: button pressed, fractal name, position, DS, group (Value/Perceptual), TA/TP, mouse position in time.

---


### References

- Ghazizadeh, A., Griggs, W., & Hikosaka, O. (2016). Object-finding skill created by repeated reward experience. *Journal of Vision*, 16(10):17, 1–13. DOI: [10.1167/16.10.17](https://doi.org/10.1167/16.10.17)

