## Image Resizer ![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/b58af5c8c9db19785a99171f2fc796a72d68cc8e3963cdcb.jpg)

---

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/fa59ed5e79680189b06aca6e740b024e61100b9a96b5269e.png)

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/971751c3ccc06db9a70ad3a97cec861643a39b0024b82e40.png)

This tool utilizes mathematical calculations and CPU power to efficiently resize images.
On the GUI side, this tool is equipped with user-friendly dialogs and a basic interface that consumes minimal system resources.

```css
body {
background: linear-gradient(to right, #A16B47, #7FC8A9);
#color effects (green, brown)
}

.image-button {
width: 100px;
height: 50px;
background-image: url('static/button.jpg');
background-size: cover;
}
```

## Management of code 🚀

---

 Used library list:

Python: OpenCV, Flask, Os, Numpy, ~~Base64~~

> First setup for OpenCV (Linux): 

`$~ sudo su`

`#~ git clone` [`https://github.com/B3B3K/auto-OpenCV-installer-`](https://github.com/B3B3K/auto-OpenCV-installer-)

`#~ cd auto-OpenCV-installer-`

`#~ chmod +x setup.sh && bash setup.sh`

**Math:** Getting value from http (demo.html) for average the color _pixel by pixel_

> Get an RGB value for each pixel → 
>
> Get an average of 5x5px (?) → 
>
> Pixe writes to another JPG by coordinates →
>
> For any errors, add extra line

```plaintext
Python3:
# Iterate over the image in split_size intervals
for y in range(0, height, split_size):
for x in range(0, width, split_size):
# Calculate the coordinates of the split area
x1 = x
y1 = y
x2 = x + split_size
y2 = y + split_size
# Extract the split area from the image
split_area = image[y1:y2, x1:x2]
# Calculate the average color of the split area
average_color = np.mean(split_area, axis=(0, 1))
# Store the average color and coordinates in the list
split_areas.append((x1, y1, x2, y2, average_color))
for i, (x1, y1, x2, y2, color) in enumerate(split_areas):
color_int = color.astype(int)
try:
for x in range(x1, x2):
for y in range(y1, y2):
blank_image[y, x, :] = color_int
except:
pass
# Handle any exceptions here
```

**Explanation of Work:**

---

> 1\. Importing Dependencies: The code imports necessary libraries such as Flask, render\_template, request, redirect, os, cv2 (OpenCV), and numpy.

> 2\. Creating Flask App: An instance of the Flask application is created using \`app = Flask(\_\_name\_\_)\`.

> 3\. Routes and View Functions:
>   - The \`@app.route('/')\` and \`@app.route('/index')\` decorators define the routes for the home page and index page, respectively. The associated view functions (\`start()\` and \`index()\`) render the corresponding HTML templates.
>   - The \`@app.route('/test\_demo', methods=\['POST'\])\` decorator defines the route for the 'test\_demo' page. The associated view function (\`execute\_function()\`) renders the 'demo.html' template.
>   - The \`@app.route('/photo', methods=\['POST'\])\` decorator defines the route for the '/photo' endpoint. The associated view function (\`calculate()\`) is responsible for processing an image.
>   - The \`@app.route('/upload', methods=\['POST'\])\` decorator defines the route for the '/upload' endpoint. The associated view function (\`upload()\`) handles image uploads.

> 4\. \`imageP()\` Function: This function processes the uploaded image by performing the following steps:
>   - Reads the image using \`cv2.imread(image\_path)\`.
>   - Retrieves the height (\`h\`) and width (\`w\`) of the image.
>   - Initializes a blank image (\`blank\_image\`) with the same height and width.
>   - Divides the image into smaller split areas based on the provided \`number\`.
>   - Calculates the average color of each split area and stores it along with the corresponding coordinates.
>   - Iterates over the split areas and fills the corresponding regions in the blank image with the average color.
>   - Saves the modified image as 'modified\_image.jpg' in the 'static/uploads' directory.

> 5\. Handling Image Upload:
>   - The \`upload()\` function handles image uploads sent via a POST request to the '/upload' endpoint.
>   - It saves the uploaded image as 'image.jpg' in the 'static/uploads' directory.
>   - Renders the 'demo.html' template and passes the image path to display the uploaded image.

>  6. Running the Application: The code includes the necessary \`if \_\_name\_\_ == '\_\_main\_\_':\` block to run the Flask.

* To Do List
1. Adding SQL thing :D
2. More effectivity for API
3. CLI version of app
4. Connecting with messaging apps
