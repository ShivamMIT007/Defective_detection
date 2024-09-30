import RPi.GPIO as GPIO
import time

# Setup Raspberry Pi GPIO (for laser and photoresistor system)
LASER_PIN = 18
PHOTO_RESISTOR_PIN = 23

# Set up GPIO
GPIO.setmode(GPIO.BCM)
GPIO.setup(LASER_PIN, GPIO.OUT)
GPIO.setup(PHOTO_RESISTOR_PIN, GPIO.IN)

def activate_laser():
    """Turn on the laser module"""
    GPIO.output(LASER_PIN, GPIO.HIGH)

def deactivate_laser():
    """Turn off the laser module"""
    GPIO.output(LASER_PIN, GPIO.LOW)

def check_laser_status():
    """Check if the photoresistor is detecting the laser beam"""
    return GPIO.input(PHOTO_RESISTOR_PIN) == 0  # 0 indicates no interruption
