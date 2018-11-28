---
layout: post
---

<!-- Page Content -->
<div class="container">
    <div class="row">
        <!-- Post Content Column -->
        <div class="col-lg-12">
            <!-- Title -->
            <h1 class="mt-4">Team Project - True Barcode Alignment</h1>
            <!-- Author -->
            <p class="lead">
            by
            <a href="#">Mohamad Zabad</a>
            </p>
            <hr>
            <!-- Date/Time -->
            <p>Posted on October 18, 2018 at 15:00</p>
            <hr>
            <!-- Preview Image -->
            <img class="img-fluid rounded" src="{{ "/assets/wall_aling.png" | prepend: site.baseurl }}" alt="Confused">
            <hr>
            <!-- Post Content -->
            <h4>In the previous episo... post... I mean post...</h4>
            <p>Although I referred to the rotation of an image as "alignment", it turns out that you can have a perfectly rotated image without having a perfectly aligned barcode.</p><br>
            <img class="img-fluid rounded" style="height: 190px; display: inline-block" src="{{ "/assets/mindblow.gif" | prepend: site.baseurl }}" alt="Gif head explode">
            <img class="img-fluid rounded" style="width: 340px; display: inline-block" src="{{ "/assets/BigMouth.gif" | prepend: site.baseurl }}" alt="Gif head explode"><br>
            <br><h4>That's where the problem starts</h4><br>
            <img class="img-fluid rounded" style="display: inline-block;width: 345px;" src="{{ "/assets/notrotnotalig.PNG" | prepend: site.baseurl }}" alt="Image of a barcdoe">
            <img class="img-fluid rounded" style="display: inline-block;width: 345px;" src="{{ "/assets/rotated_not_aligned.png" | prepend: site.baseurl }}" alt="Image of a barcdoe"><br><br>
            <p>As you can see form the pictures above, the first one is a barcode that is neither rotated, nor aligned, while the second one is perfectly rotated but the alignment of the bars is off. This has proven to be quite a challenege for all of my team because our solution relied on decently aligned images in order to decode the information contained inside them. </p>
            <p>Did my solution prove effective? Not really...</p><br>
            <img class="img-fluid rounded" style="display: inline-block;width: 345px;" src="{{ "/assets/rotated_not_aligned.png" | prepend: site.baseurl }}" alt="Image of a barcdoe">
            <img class="img-fluid rounded" style="display: inline-block;width: 345px;" src="{{ "/assets/aligned.PNG" | prepend: site.baseurl }}" alt="Image of a barcdoe"><br><br>
            <p>While this is the worst case scenario, you don't really want to put in your code a solution that works only at times. Unless your standards are so low that you'd be happy with a 70% success rate and 30% disaster, then there you go, problem solved.<br> In my team we did take this as a serious issue and after discussing with my team members, Ben Ryan and Rober Vaughan, we decided to keep it out of the final solution.</p>
            <img class="img-fluid rounded" src="{{ "/assets/align_code.PNG" | prepend: site.baseurl }}" alt="Image of a barcdoe"><br><br>
            <p>Behold the code! Don't worry because we will have a quick run down through it and we will explain every bit of it. If you have read the previous blog post, you will see that I am re-using a bit of the code there, especially at the start. However, from the part where Canny is applied, it's all new!</p>
            <p>In this code we:</p>
            <ul>
                <li>Convert to Grayscale</li>
                <li>Blur the image with a Gaussian Blur</li>
                <li>Reverse the colours with a bitwise_not on the blurred image</li>
                <li>Apply Canny </li>
                <li>Get the structure element after merging the image by the size multiplied by .2</li>
                <li>Dilate the element with the mentioned Canny on the structured element</li>
                <li>Get another structred element after the dilation which should show a big element consisted of the whole barcode instead of little pieces this time</li>
                <li>Apply morphologyEx wich is just erosion followed by dilation in order to remove any noise created</li>
                <li>Find the countour of the barcode</li>
                <li>Find the biggest contour area and assume that it is the barcode</li>
                <li>Find the rectangle that fits all the contour with minAreaRect</li>
                <li>Get the points of the rectangle (corners)</li>
                <li>Apply findHomography to determine the change neededd to be applied in order to go from the current positions of the corners to the corners of the image</li>
                <li>Apply the said homography with warpPerspective on the original picture so the barcode appears aligned</li>
            </ul>
            <br><br><br>
            <h5>References used:</h5>
            <a href="https://www.pyimagesearch.com/2014/05/05/building-pokedex-python-opencv-perspective-warping-step-5-6/">https://www.pyimagesearch.com/2014/05/05/building-pokedex-python-opencv-perspective-warping-step-5-6/</a><br>
            <a href="https://docs.opencv.org/2.4/modules/imgproc/doc/geometric_transformations.html">https://docs.opencv.org/2.4/modules/imgproc/doc/geometric_transformations.html</a><br>
            <a href="https://www.learnopencv.com/tag/warpperspective/">https://www.learnopencv.com/tag/warpperspective/</a><br>
            <a href="https://www.programcreek.com/python/example/89422/cv2.warpPerspective">https://www.programcreek.com/python/example/89422/cv2.warpPerspective</a><br>
            <a href="https://stackoverflow.com/questions/53463144/opencv-python-align-4-corners-of-an-element">My shameless stack overflow post</a><br>
        </div>
    </div>
    <!-- /.row -->
</div>
<!-- /.container -->


