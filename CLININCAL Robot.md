- embedde linux
	- 4 tools for building embedded linux
		- yocto
		- build root 
		- openwrtl
		- desktop  distros

- room detection using images  project :
	- https://medium.com/bbm406f18/week-1-object-detection-and-room-classification-with-deep-learning-63f72e7964ac

- workflow 
	- create an ml program to detect  different numbers 
	- using the model create a prograto lightup different led 
	- using lidar create a room scanning system 
	- integrate both ml and lidar section
	-  create a line detection robot 
		-  impliment reinforcement learning to detect and move from a room.

- from Ieee paper 
	- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4481921/#:~:text=Our%20automatic%20scanning%20system%20is,starts%20scanning%20an%20adjacent%20room
	- the octree space is considered , where the heights of the 3d space is projected into the 2d sace . the infp regarding walls of the room are trimmered out to redue the size of overall data . here the 3d space is sliced into different slices and the optimal slice is taken under consideration . the NBV ( next best view problem ) its a uestion that arises when the best posiilbe scan can be taken .