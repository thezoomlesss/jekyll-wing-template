---
layout: post
---

<!-- Page Content -->
<div class="container">
    <div class="row">
        <!-- Post Content Column -->
        <div class="col-lg-12">
            <!-- Title -->
            <h1 class="mt-4">Team Project - Barcode Alignment</h1>
            <!-- Author -->
            <p class="lead">
            by
            <a href="#">Mohamad Zabad</a>
            </p>
            <hr>
            <!-- Date/Time -->
            <p>Posted on October 19, 2018 at 17:00</p>
            <hr>
            <!-- Preview Image -->
            <img class="img-fluid rounded" src="{{ "/assets/lost.jpg" | prepend: site.baseurl }}" alt="Confused">
            <hr>
            <!-- Post Content -->
            <h4>Where do I start?</h4>
            <p>Having little to no experience with Image processing and having to solve a problem where you need to understand at least the basiscs of OpenCV can seem a bit daunting at first. Without the base already set up in your mind and knowing which path you should follow, you quickly realise that you've been stuck at the first page of google search, having no clue what to look up.</p><br>
            <img class="img-fluid rounded" src="{{ "/assets/google.PNG" | prepend: site.baseurl }}" alt="Image of the homepage of google search"><br>
            <h4>Attempt one: Find the first and last bar of the barcode</h4>
            <p>The idea here was to figure out the orientation of the barcode by using the only 2 points that are surely different from the rest of the element.<br>
            Normally, the barcodes we were using started with a long bar at the start and ended with another one. In theory, this was a great idea as I could've used that and compared it to the rest of the element to figure out if it was upside down.</p>
            The problem is that the barcode looks like this normally:<br>
            <img class="img-fluid rounded" src="{{ "/assets/barcode-clean.PNG" | prepend: site.baseurl }}" alt="Image a barcode"><br><br>
            This would be the ideal case when the barcode is clean, there is no noise involved and it allows us to run few lines of code to isolate the bars.
            My approach tried to turn an image into grayscale and use a gradient to separate the bars, but that turned out to be a mess as shown below:<br><br>
            <img class="img-fluid rounded" src="{{ "/assets/barcode-dirty.PNG" | prepend: site.baseurl }}" alt="Image a barcode"><br><br>
            <img class="img-fluid rounded" src="{{ "/assets/code1.PNG" | prepend: site.baseurl }}" alt="Image of code"><br><br>
            <h4>Attempt two: Find the corners and use them as reference</h4>
            <p>With the previous attempt failing, I found an interesting idea where you would have to look for the corners of an angled barcode. Picking those will allow us to compare the positioning of the first two corners. By taking those points and calculating how much of a shift in the rotation is needed in order to level those two points, we can get the barcode to display nicely.</p><br>
            <p>While some results were promising in the testing, others failed horribly if the corners were not detected properly. So I needed a new plan...<br>
            <h4>Attempt three: NOW OR NEVER</h4>
            With a lot of googling and time spent on understanding some pretty basic concepts (which make me look back now and realise how little I knew), I managed to put together this code:</p><br>
            <p>What this does, instead of looking for corners, it tries to find the biggest structured element and draws the minimum rectangle that covers all the points of interest. By using the coordonates of the rectangle, we calculate the angle needed for clockwise or counterclockwise shift in order for the barcode to be finally displayed correctly.</p>
            <img class="img-fluid rounded" src="{{ "/assets/code2.PNG" | prepend: site.baseurl }}" alt="Another image of code"><br><br>
            <img class="img-fluid rounded" src="{{ "/assets/angle.PNG" | prepend: site.baseurl }}" alt="Re-angled image"><br><br>
            <p>In this case and on similar images with QR codes, it seems to do the trick quite well, with little trouble when tested on some particular images. This can definitely be improved in the future...</p>
            <br><br><br>
            <h5>References used:</h5>
            <a href="https://docs.opencv.org/3.4.3/db/dd6/classcv_1_1RotatedRect.html">https://docs.opencv.org/3.4.3/db/dd6/classcv_1_1RotatedRect.html</a><br>
            <a href="https://docs.opencv.org/2.4/doc/tutorials/imgproc/shapedescriptors/bounding_rotated_ellipses/bounding_rotated_ellipses.html">https://docs.opencv.org/2.4/doc/tutorials/imgproc/shapedescriptors/bounding_rotated_ellipses/bounding_rotated_ellipses.html</a><br>
            <a href="https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_imgproc/py_geometric_transformations/py_geometric_transformations.html">https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_imgproc/py_geometric_transformations/py_geometric_transformations.html</a><br>
            <a href="https://www.pyimagesearch.com/2017/01/02/rotate-images-correctly-with-opencv-and-python/">https://www.pyimagesearch.com/2017/01/02/rotate-images-correctly-with-opencv-and-python/</a><br>
            <a href="https://www.pyimagesearch.com/2017/02/20/text-skew-correction-opencv-python/">https://www.pyimagesearch.com/2017/02/20/text-skew-correction-opencv-python/</a><br>
            <a href="https://stackoverflow.com/questions/9041681/opencv-python-rotate-image-by-x-degrees-around-specific-point">https://stackoverflow.com/questions/9041681/opencv-python-rotate-image-by-x-degrees-around-specific-point</a><br>
            <a href="https://www.tutorialkart.com/opencv/python/opencv-python-rotate-image/">https://www.tutorialkart.com/opencv/python/opencv-python-rotate-image/</a><br>
            
        </div>
    </div>
    <!-- /.row -->
</div>
<!-- /.container -->



