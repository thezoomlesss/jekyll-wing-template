---
layout: post
---

<!-- Page Content -->
<div class="container">
    <div class="row">
        <!-- Post Content Column -->
        <div class="col-lg-12">
            <!-- Title -->
            <h1 class="mt-4">Team Project - Barcode Reconstruction</h1>
            <!-- Author -->
            <p class="lead">
            by
            <a href="#">Mohamad Zabad</a>
            </p>
            <hr>
            <!-- Date/Time -->
            <p>Posted on October 21, 2018 at 15:27</p>
            <hr>
            <!-- Preview Image -->
            <img class="img-fluid rounded" src="{{ "/assets/wall_reconstruction.png" | prepend: site.baseurl }}" alt="barcode">
            <hr>
            <!-- Post Content -->
            <h4>The last push</h4>
            <p>Well, it is about time I start talking about the most difficult issue I've encountered while working on this project. Due to the amount of time spent on the true alignment from the previous post, I was left with almost no time to figure out how to reconstruct a broken barcode. I had hoped that there would be an amazing saviour online that I definitely do not deserve, but such opportunity did not show itself. All I could find were barely relevant solutions... Even though, thinking about it know, in the past I did lose hours of googling just because I was using the wrong term, so it could just be my inability to find relevent data online. Who knows?</p><br>
            <img class="img-fluid rounded" style="display: inline-block;width: 345px;" src="{{ "/assets/rotated_not_aligned.png" | prepend: site.baseurl }}" alt="Image of a barcdoe"><br><br>
            <p>My least brilliant idea was to use a very difficult image as my test image. Why did I do that, you might ask? Well, the thought process worked this way:<br>
            <ul>
            <li>If I can rotate a difficult image then I can rotate any image</li>
            <li>If I can align a difficult image then I can rotate any image</li>
            <li>If I can reconstruct a difficult image then I can rotate any image</li>
            </ul><br>And what do you know? Rotation worked, but alignment didn't give the expected results and it proved to be deadly for the progress of the reconstruction of a barcode.<br>With this in mind, let's go through some of the ideas that I came up with.</p><br>
            <br><p>If a barcode has a black pixel on the top row or on the bottom one, that means that the entire column should be black, unless that pixel is there due to noise or any other unnatural reason. In theory, this idea should work but the cases where it worked were too small to be taken into account. Most bars were wider than a single pixel and some of them were not as wide as others. <br> I believe that with enough time, I would've been able to implement a solution that would've fixed this issue, based on this idea, but due to other assignments being around the corner and limited time, I did not manage to implement this idea.</p>
            <br><br><br>
            <h5>References used:</h5>
            <a href="https://stackoverflow.com/questions/43859750/how-to-connect-broken-lines-in-a-binary-image-using-python-opencv">https://stackoverflow.com/questions/43859750/how-to-connect-broken-lines-in-a-binary-image-using-python-opencv</a><br>
        </div>
    </div>
    <!-- /.row -->
</div>
<!-- /.container -->


