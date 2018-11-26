---
layout: post
---

<!-- Page Content -->
<div class="container">
    <div class="row">
        <!-- Post Content Column -->
        <div class="col-lg-12">
            <!-- Title -->
            <h1 class="mt-4">Team Project - Improved Barcode Alignment</h1>
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
            <img class="img-fluid rounded" src="{{ "/assets/angle.PNG" | prepend: site.baseurl }}" alt="Confused">
            <hr>
            <!-- Post Content -->
            <h4>On a more serious note...</h4>
            <p>For my project that I am doing for my Image Processing class, I have been tasked with the responsability of handling the image rotation. That means that my goal would be to take an image as an input, rotate it to the right alignment and then pass the rotated image to my colleagues part of the code, where the rest of the magic can happen.<br>Here we can have a look at the code that does this for us and below we will see an explanation.</p><br>
            <img class="img-fluid rounded" src="{{ "/assets/rotated.PNG" | prepend: site.baseurl }}" alt="Image code used for rotation"><br>
            <h4>Some of the results produced on barcodes and QR codes</h4>
            <img class="img-fluid rounded" style="display: inline-block,width: 345px;" src="{{ "/assets/5R5mX0JX.jpg" | prepend: site.baseurl }}" alt="Image of a barcdoe">
            <img class="img-fluid rounded" style="display: inline-block,width: 345px;" src="{{ "/assets/qr_code_rotated.PNG" | prepend: site.baseurl }}" alt="Image of a barcdoe"><br><br>
            <img class="img-fluid rounded" style="display: inline-block,width: 345px;" src="{{ "/assets/barcodediag.jpg" | prepend: site.baseurl }}" alt="Image of a barcdoe">
            <img class="img-fluid rounded" style="display: inline-block,width: 345px;" src="{{ "/assets/Barcode_out.jpg" | prepend: site.baseurl }}" alt="Image of a barcdoe"><br><br>
            <img class="img-fluid rounded" style="display: inline-block,width: 345px;" src="{{ "/assets/BackCover_CreateSpaceAutoBarcode.jpg" | prepend: site.baseurl }}" alt="Image of a barcdoe">
            <img class="img-fluid rounded" style="display: inline-block,width: 345px;" src="{{ "/assets/rotated_barcode_2.PNG" | prepend: site.baseurl }}" alt="Image of a barcdoe"><br><br>
            <p>This code follows closely the idea of the code found in the previous post, with the one difference being that this one is improving the algorithm by first applying a GaussianBlur before thresholding so it gives better results on lower quality images. This has proven to be a great improvement on images that we found to be more difficult to deal with.</p>
            <p>The sequence the code is following is simple:
            <ul>
                <li>Convert to Grayscale</li>
                <li>Blur the image with a Gaussian Blur</li>
                <li>Reverse the colours with a bitwise_not on the blurred image</li>
                <li>Apply the threshold</li>
                <li>Store the positive pixel locations ( 0 is off and 1 is on )</li>
                <li>Determine the angle needed to align everything with minAreaRect</li>
                <li>Test against the angle to see the direction of rotation</li>
                <li>Get the center and calculate the rotation matrix needed to be applied</li>
                <li>Rotate with warpAffine and return the image </li>
            </ul>
            </p>
        </div>
    </div>
    <!-- /.row -->
</div>
<!-- /.container -->


