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
            <p>Posted on October 13, 2018 at 15:00</p>
            <hr>
            <!-- Preview Image -->
            <img class="img-fluid rounded" src="{{ "/assets/lost.jpg" | prepend: site.baseurl }}" alt="Confused">
            <hr>
            <!-- Post Content -->
            <h4>Where do I start?</h4>
            <p>Having little to no experience with Image processing and having to solve a problem where you need to understand at least the basiscs of OpenCV can seem a bit daunting at first. Without the base already set up in your mind and knowing which path you should follow, you quickly realise that you've been stuck at the first page of google search, having no clue what to look up.</p><br>
            <img class="img-fluid rounded" src="{{ "/assets/google.png" | prepend: site.baseurl }}" alt="Image of the homepage of google search"><br>
            <h4>Attempt one: Find the first and last bar of the barcode</h4>
            <p>The idea here was to figure out the orientation of the barcode by using the only 2 points that are surely different from the rest of the element.<br>
            Normally, the barcodes we were using started with a long bar at the start and ended with another one. In theory, this was a great idea as I could've used that and compared it to the rest of the element to figure out if it was upside down.</p>
            The problem is that the barcode looks like this normally:<br>
            <img class="img-fluid rounded" src="{{ "/assets/barcode-clean.png" | prepend: site.baseurl }}" alt="Image a barcode"><br><br>
            This would be the ideal case when the barcode is clean, there is no noise involved and it allows us to run few lines of code to isolate the bars.
            My approach tried to turn an image into grayscale and use a gradient to separate the bars, but that turned out to be a mess as shown below:<br><br>
            <img class="img-fluid rounded" src="{{ "/assets/barcode-dirty.png" | prepend: site.baseurl }}" alt="Image a barcode"><br><br>
            <p>With this piece of code that would be ideal if we would want to find the barcode, but not useful when trying to find particular parts of it.</p>
            <img class="img-fluid rounded" src="{{ "/assets/code1.png" | prepend: site.baseurl }}" alt="Image of code"><br><br>
            <p>With the previous attempt failing, I found an interesting solution that works for angled pictures that will take the higest point they find of a corner and the second highest points of another corer (which normally should be on the same height), and calculates the angle that needs to be applied in order for these two points to be on the same level.<br>Here is an example of it + the code:</p><br>
            <img class="img-fluid rounded" src="{{ "/assets/angle.png" | prepend: site.baseurl }}" alt="Re-angled image"><br>
            <img class="img-fluid rounded" src="{{ "/assets/cod2.png" | prepend: site.baseurl }}" alt="Another image of code"><br>
            <p>In this case and on similar images with QR codes, it seems to do the trick quite well, with little trouble when tested on some particular images.</p>
        </div>
    </div>
    <!-- /.row -->
</div>
<!-- /.container -->



