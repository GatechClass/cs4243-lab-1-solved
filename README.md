# cs4243-lab-1-solved
**TO GET THIS SOLUTION VISIT:** [CS4243 Lab 1 Solved](https://mantutor.com/product/cs4243-instructions-solved-5/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113851&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS4243 Lab 1 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
Upload to Canvas your completed lab1.py and lab1.ipynb by zipping them into a file named AXXX1_AXXX2.zip, where AXXX is the student number of the group members. Submit one file per group. Missing files, incorrectly formatted code that does not run, etc. will be penalized.

Objective

This lab allows you to familiarize yourself with basic image pre-processing steps and learn about template matching. Template matching applies (normalized) cross-correlation to find local maxima at locations of the image that are similar to the template. From the local maxima, we can find repeating patterns in the image (see Fig. 1).

Figure 1: Overview of this lab. (a) Original image, with template denoted by red box (b) template matching result, where black and white indicates weak and strong matches respectively.

Part 1: Image Preprocessing (15%)

This part implements some basic pre-processing functions required in this lab.

• pad_zeros()adds a border of zeros around the input images so that the output size will match the input size after a convolution or cross-correlation operation. Do not to use numpy.pad() or other OpenCV functions to implement this function.

• rgb2gray() converts a colour image to greyscale. Use (0.299, 0.587, 0.114) as the weights for red, green and blue channels respectively.

Part 2: Normalized Cross-Correlation (30%)

This part explores three implementations of various efficiencies for normalized cross-correlation. Implement the following three functions.

• normalized_cross_correlation()is a naïve version using 4, 5 or 6 nested for-loops iterating over the output and the template. The 4 loops include the height, width of the image, height, width of the template. You can also loop over the channel and there will be 5 or 6 forloops in total.

• normalized_cross_correlation_fast()implements the cross correlation with 2 or 3 nested for-loops. The for-loop over the template is replaced with the element-wise multiplication between the kernel and the image regions.

• normalized_cross_correlation_matrix()converts cross-correlation into a matrix multiplication operation to leverage optimized matrix operations e.g. numpy.matmul. To re-formulate as a matrix multiplication, you will need to reshape the template and input image . o The matrix multiplication to perform is 𝐗r = 𝐏r𝐅r, where 𝐏r and 𝐅𝐫 are reshaped image and template matrices respectively and 𝐗r is a reshaped output.

o 𝐅r has dimensions [hFwF × 1] where hF and wF are the kernel dimensions o 𝐏r has dimensions [hXwX × hFwF] where hX and wx are the input image dimensions before zero-padding with duplicated elements from the input.

o 𝐗r needs another reshape to get the original 2D cross-correlation output 𝐗 o For the normalization term 1 , the summation operations for computing the

|𝑭||𝒘𝑖𝑗|

magnitudes can also be solved as “correlation” with a filter or kernel of 1s.

• Generalize your three implementations for colour inputs and templates.

o Consider the R, G, and B channels as a third dimension of the input image and template matrix. The normalized cross-correlation can be expressed as, with c as the channel index

𝑘 𝑘 3

𝑥𝑖𝑗 ∑ ∑ ∑ 𝑓𝑢𝑣𝑐 ∙ 𝑝𝑖+𝑢,𝑗+𝑣,𝑐

|𝑭||𝒘𝑖𝑗| 𝑢=−𝑘 𝑣=−𝑘 𝑐=1

o Re-arranging the matrices for matrix version for coloured images and templates is a bit trickier. Refer to Fig. 2 to help visualize the reshaping operation. The new 𝐅r will have dimensions [3hFwF × 1] while the new 𝐏r will have dimensions [hXwX × 3hFwF]

Figure 2: Reshaping operation in normalized_cross_correlation_matrix().

Part 3: Non-Maximum Suppression (10%)

The matched template locations occur at local maximum in the output 𝐗. These maxima can be found via a non-maximum suppression procedure. We will use a greedy form by iteratively finding the global maximum and zeroing the neighbouring region.

• non_maximum_suppression()

1. Set a threshold 𝜏; values in 𝐗&lt;𝜏 will not be considered. Set 𝐗&lt;𝜏 to 0.

2. While there are non-zero values in 𝐗

a. Find the global maximum in 𝐗 and record the coordinates as a local maximum.

b. Set a small window of size 𝑤 × 𝑤 points centered on the found maximum to 0.

3. Return all recorded coordinates as the local maximum.

Figure 3: Sample output for normalized cross-correlation with non-maximum suppression, with each found maximum visualized by a red dot.

Part 4: Study on Template Matching (45%)

This part explores the various parameters that affects our template matching results. You are also asked to implement a more “practical” version of normalized cross-correlation.

• Image Inputs (5%). Apply template matching to the same image in greyscale, RGB or as a set of gradient images. You can consider the gradient images analogous to an RGB image but with 4 channels instead. Verify that you get similar maxima for all three types of inputs.

• Template Inputs (6%). Consider the rectangular.jpg image. Apply the supplied templates of different patterns and compare the normalized cross-correlation outputs with show_img_with_points(). o Explain why their response positions are different.

• Template Size (6%). Consider the holes.jpg image and compare the normalized crosscorrelation outputs with show_img_with_points()using four different templates with a grid of 1×1, 1×3, 3×1 vs. 3×3 holes.

o How can each of these templates to detect every hole present in the input image?

o Analyze and explain the subtle differences in the output borders.

o Describe the correlation output with templates with a 1×1.5 or a 1×2 array of holes.

• Mean-subtracted cross correlation (16%). It is more common in practice to subtract the mean from the image window and template before applying normalized cross-correlation. For colour images, the means are calculated separately for each channel, i.e.

𝑘 𝑘 3

𝑥𝑖𝑗 ∑ ∑ ∑ 𝑓′𝑢𝑣𝑐 ∙ 𝑝′𝑖+𝑢,𝑗+𝑣,𝑐

|𝑭′||𝒘′𝑖𝑗| 𝑢=−𝑘 𝑣=−𝑘 𝑐=1

where 𝑓′𝑢𝑣𝑐 = 𝑓𝑢𝑣𝑐 𝑘 ∑𝑘𝑣′=−𝑘 𝑓𝑢′𝑣′𝑐 are elements of the mean-subtracted template 𝑭′ and 𝑝′𝑖𝑗𝑐 = 𝑝𝑖𝑗𝑐 𝑘𝑣′=−𝑘 𝑝𝑖−𝑢′,𝑗−𝑣′,𝑐, are elements of the meansubtracted input window 𝒘′𝑖𝑗.

o normalized_cross_correlation_ms(). Implement this function based on the equations above; for simplicity, use the “fast” version.

o Apply the mean-subtracted cross correlation with the provided templates to holes.jpg; compare the outputs with the version which does not subtract the mean. What are the benefits of subtracting the mean?

• Auto-correlation (6%). Cross-correlates input image with itself (i.e. uses the entire image as a template). Apply the provided auto-correlation implementation to holes.jpg, and observe the response map. Explain why the correlation output responses decrease as one gets further away from the center of the output.

• Limitations (6%). Apply template matching with any version of the cross-correlations to chairs.jpg. Observe the outputs and explain why template matching fails in certain regions.
