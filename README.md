# image-preview-before-upload-using-javaScript

Viewing an image before is one of the best feature that every website must provide to their user. It allows user to check whether they are going to upload the correct image or not, or if the image looks good or not.

&nbsp;

In this tutorial we are going to build this functionality of viewing image before upload using JavaScript and JQuery.

&nbsp;
<h2>HTML Code</h2>
&nbsp;
<pre class="article_code"><code data-language="html">
&lt;div class="wrap"&gt;

&lt;div class="header"&gt;Image Preview Before Upload using JavaScript &lt;/div&gt;
&lt;form method="post" action=""&gt;
&lt;label for="upload"&gt;Upload Image: &lt;/label&gt;
&lt;input type="file" name="upload" id="upload" onchange="previewImage(this);"&gt;
&lt;/form&gt;

&lt;div id="preview"&gt;
&lt;h3&gt;Image Preview&lt;/h3&gt;
&lt;img src="http://via.placeholder.com/380x200" id="preview-image"&gt;
&lt;/div&gt;

&lt;/div&gt;
</code></pre>
&nbsp;
<h2>CSS Code</h2>
&nbsp;
<pre class="article_code"><code data-language="css">
.wrap{
  width:400px;
  margin-left:auto;
  margin-right:auto;
  font-family: sans-serif;
  box-shadow:1px 1px 5px #ccc;
}
.header{
  background: #f2f2f2;
  margin:0px 0px 0px 0px;
  padding:20px;
  border-bottom:1px solid #f2f2f2;
  font-weight:normal;
}
form{
  padding:10px 10px 0px 10px;
}
input[type="file"]{
  padding: 5px 10px;
  border:1px solid #ccc;
  margin: 5px 5px 5px 0px;	
}
input[type="submit"]{
  background: #333;
  color: #fff;
  padding: 10px 5px;
  border:1px solid #333;
  cursor:pointer;
}
h3{
  font-weight:normal;
}
#preview{
  padding:0px 10px 10px 10px;
}
#preview-image{
  background: #333;
  min-height:200px;
  width: 100%;
}
</code></pre>
&nbsp;
<h2>JavaScript Code</h2>
<strong>NOTE</strong>: Include jquery file.

The core part of this program is in JavaScript. The <strong>previewImage</strong> function takes the input image. The <strong>FileReader</strong> <span class="st">object lets web applications asynchronously read the contents of files</span>.

&nbsp;
<pre class="article_code"><code data-language="html">
&lt;script src="jquery-1.9.1.js"&gt;&lt;/script&gt;
&lt;script&gt;
function previewImage(input) {
  if (input.files &amp;&amp; input.files[0]) {
    var reader = new FileReader();
    reader.onload = function (e) {
      $('#preview-image').attr('src', e.target.result);
    }
    reader.readAsDataURL(input.files[0]);
  }
}
&lt;/script&gt;
</code></pre>

#Visit My Blog: <a href="http://idiotdeveloper.tk">idiotdeveloper.tk</a>
