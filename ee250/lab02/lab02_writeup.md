Demo Video Google Drive Link: https://drive.google.com/file/d/1g2wqPWQEIRMVBHLonG6D-ZgGWBbdCHyv/view?usp=sharing

4.1 Suppose you just cloned a repository that included one python file, my_first_file.py, and you now want to add a second file to your repository named my_second_file.py and push it to Github.com. Complete the sequence of linux shell commands:
		
		git clone git@github.com:my-name/my-imaginary-repo.git
		cd my-imaginary-repo
		touch my_second_file
		git add my_second_file.py
		git commit -m "my second file"
		git push
		##complete the sequence

(Note: create the file using the `touch` command)

4.2 Describe the workflow you adopted for this lab (i.e. did you develop on your VM and push/pull to get code to your RPi, did you edit files directly on your RPi, etc.).  Are there ways you might be more efficient in the next lab (i.e. learning a text-based editor so you can edit natively on the RPi, understanding Git commands better, etc.)?

At first I started editing the grovepy_sensors.py file on my VM using the Sublime text editor. However, I quickly realized that it was much easier and more efficient to edit the file directly in the RPi using nano. I was able to test and debug my code much faster editing in the RPi command line using nano rather than editing in sublime on my VM where I would have to continuously add, commit, push, and pull before being able to test my code. I would definitely benefit from understanding the Git commands better, as well as understanding the nano shortcuts. 


4.3 In the starter code, we added a 200 ms sleep. Suppose you needed to poll the ultrasonic ranger as fast as possible, so you removed the sleep function. Now, your code has just the function ultrasonicRead() inside a while loop. However, even though there are no other functions in the while loop, you notice there is a constant delay between each reading. Dig through the python library to find out why there is a constant delay. What is the delay amount? In addition, what communication protocol does the Raspberry Pi use to communicate with the Atmega328P on the GrovePi when it tries to read the ultrasonic ranger output using the `grovepi` python library?

The delay amount is 60 ms - this is included because the firmware needs 50 ms to write and read to the i2c command that communicated with the Atmega328P. it uses an i2c serial communication protocol so that data is transferred one bit at a time.


