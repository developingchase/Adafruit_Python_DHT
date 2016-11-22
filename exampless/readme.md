#TEMHUM
This project measures the readings of an Adafruit DHT sensor and records them. I execute it via a crontab job every 5 minutes.

1) Create the SQLITE3 DB:
  sqlite3 temhum.db
  CREATE TABLE temhum(date date, tem float, hum float);
2) Add to crontab (22 is the sensor type, 4 is the GPIO pin I'm using on my Pi):
  */5 * * * * python /home/pi/temhum.py 22 4 > /dev/null 2>&1
  
#Next steps
- Graph the results with NodeJS (PiThermServer)
- Pull from the OpenWeather API to track the outside tem/hum and compare them on the same graph
