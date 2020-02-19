- To install use pip.

```bash
sudo pip3 install pyserial
```

- Open up a text editor or your preferred Python IDE

- To read serial data, you can use the Python serial library.

```python
import serial
```

- You need to specify the serial port you art using when you create your serial object. For instance:

```python
import serial

ser = serial.Serial('/dev/ttyUSB0')
```

- Additionally you may need to specify settings that are specific to the device that is communicating using the serial communication protocol.

```python
ser = serial.Serial('dev/ttyUSB0',
                    baudrate=9600,
					parity=serial.PARITY_NONE,
					stopbits=serial.STOPBITS_ONE)
```
Bytes are sent from your device to your computer at a set frequency. Flow control for serial communication works on the principles of First In First Out (FIFO). So when you call `pmd.read()` you are reading the oldest byte in the input buffer.

Add two lines to store and the print out the oldest byte in the input buffer

```python
data = pmd.read()
print(byte)
```


If you want to read more than a single byte, you can specify how many bytes to read

```python
data = pmd.read(10)
print(bytes)
```

- Once you have read the bytes, they are removed from the input buffer.

- If you need to clear the input buffer, to remove old data, you can use the following line.

```python
pmd.reset_output_buffer()
```

- Lastly, although when you look at the bytes, they appear to be a string, the bytes object is in reality a series of integers. If you want to see the value of a single byte in your bytes object, you can index it directly.

- Add the following lines to view the values of specific bytes. This will output the integer values of the bytes.

```python
first_byte = data[0]
second_byte = data[1]

print(first_byte, second_byte)
```

- For more information on using the `pyserial` modules you can have a look at the documentation - https://pyserial.readthedocs.io/en/latest/
