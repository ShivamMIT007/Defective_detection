from flask import Flask, render_template, Response, jsonify
import camera
import sensor

app = Flask(__name__)

# Home Page
@app.route('/')
def index():
    return render_template('index.html')

# Route to stream camera feed
@app.route('/video_feed')
def video_feed():
    return Response(camera.gen_frames(), mimetype='multipart/x-mixed-replace; boundary=frame')

# Route to check laser module status
@app.route('/laser_status')
def laser_status():
    laser_active = sensor.check_laser_status()  # Check if laser is functioning
    return jsonify({'status': laser_active})

# Route to manually turn the laser system on
@app.route('/turn_laser_on', methods=['POST'])
def turn_laser_on():
    sensor.activate_laser()
    return jsonify({'status': 'Laser activated'})

# Route to manually turn the laser system off
@app.route('/turn_laser_off', methods=['POST'])
def turn_laser_off():
    sensor.deactivate_laser()
    return jsonify({'status': 'Laser deactivated'})

if __name__ == '__main__':
    app.run(debug=True)
