**Finding Lane Lines on the Road**
The Goals / steps of this project are the following:
    Make a pipeline that finds lane lines on the read
    Reflect on my work in a written report.

Reflection
    my pipeline first imports a frame from the video. Next, it performs a Canny edge detection to find all the
    edges in the image. Then, region select is preformed only showing a quadrilateral portion of the bottom of
    the image where the lane lines should be. After that, the HoughLinesP function transforms the "edges" image 
    (the output from canny) into an array of lines, next they are sorted into “leftx, lefty, rightx, righty” 
    for the left and right lane line, x and y coordinates. to ensure no points were added to the wrong side I 
    made an if statement that would find the slope and which side of the image the point was on, I added the
    last part during tweeking because the lines were off in a few frames when other non-lanelines were on the
    road. the coordinates for each side are then pluged into numpy’s polyfit function to give the best fit 
    along the points. an equation for the top and the bottom point of the lane lines is made then those points 
    are used to draw the line on to the image. 
Shortcomings
    Some protental short comings are that the left and right lane lines might not be in the exact center of the
    image, some points do get kicked out of both lists, another is that the pipeline only draws straight lines
    so the program will not work well for curved sections of road. 
Suggestions for improvements
    Possible improvements include averaging the left and right points to find the middle point between the
    two line segments, and using a higher degree polyfit to be able to make curved lines.
