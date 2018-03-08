#  iOS App demo

Pre-requisites: To run this tutorial you should be using MacOS with XCode v9 installed

## Setup XCode sample

Step 1. Make sure your Custom vision model is setup as "Compact". This can be checked and changed in model Settings. Export your model in CoreML format

Step 2. Open iOS app project in XCode IDE provided in ```
Note: The sample used for this tutorial has been developed by explained at the blogpost [
"Introduction to Core ML: Building a Simple Image Recognition App"](https://www.appcoda.com/coreml-introduction/).

Step 3. Run in simulator, select "Library" to select any existing image. You can add any image to the library by drag & drop.
The bottom text should show "Analyzing image ... "  as on the screenshot below.


## Add CoreML model

Step 1. Upload your custom model into to root of the project, and make sure you select a checkbox "Target Membership"

See screenshot below

Step 2. Open ViewController.swift file

Define ```model``` variable at the top of the class. Use the name of your mlmodel file for class type.
```
var model: artworks!

```
Step 3. After the model variable has been defined create a method which will initialise that model.
```
override func viewWillAppear(_ animated: Bool) {
  model = artworks()
}


```

Step 4. Add the code below right after the last line in the imagePickerController function

```
    guard let prediction = try? model.prediction(data: pixelBuffer!) else {
    return
    }

    classifier.text = "Hey, it looks like \(prediction.classLabel)."
}
```

Note: imagePickerController function specifies the image size required by the model. If your model requires a different width and height of the image please check line 63 onwards ("// IMPORTANT: Set up the width and height of the image as expected by the ML Model input")

## Run classification for any image

Step 1. Run simulator again for an updated project

Step 2. Use a validation image to run prediction against ML model available on device (you can test by switching off wifi on your mac)


