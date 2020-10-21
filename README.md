# Hacktoberfest-Repository

Have you ever encouted the problem when you need a metronome but do not have one? Now, with just a multi function microbit, you can easily have a metronome with a microbit! Key in the below code and enjoy! 

from microbit import *
import music
index=60
display.scroll(str(index))
while True:
  music.play("C:4")
  music.set_tempo(ticks=1, bpm=index)
  if button_a.was_pressed():
    index = 100
    display.scroll(str(index))
  if button_b.was_pressed(): 
       index = index + 20
       display.scroll(str(index))
  if index >= 220:
    index = 60   
    display.scroll(str(index))
  if accelerometer.was_gesture('shake'):
    display.scroll('Hello')
    break
