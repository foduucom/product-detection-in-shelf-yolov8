# Product detection in shelf Yolo V8
![](https://github.com/foduucom/product-detection-in-shelf-yolov8/blob/main/thumbnail.jpg)
## Model Card for YOLOv8 Shelf Object Detection in Retail Environments
## Model Enthusiasm 🎉
Hey there, retail rockstar! 👋 If you're ready to make your mart or mall experience a whole lot cooler, give this YOLOv8 Shelf Object Detection model a virtual high-five! 🙌 Your shelves will never be the same again, and neither will your customers' smiles.

## Model Magic ✨
The YOLOv8 Shelf Object Detection model is your new retail sidekick! It doesn't just detect objects; it's got a sixth sense for finding what you need on those shelves. Whether it's a jar of pickles or the latest gadget, this model's got you covered. And hey, it's a pro at counting too! So, say goodbye to empty spaces and hello to perfectly organized retail enchantment.

### Supported Labels 🏬
```
['Empty Shelves', 'Magical Products']
```

### How to get started with the model
To dive into the retail wizardry with the YOLOv8 Shelf Object Detection model, follow these enchanted steps:
```
pip install ultralyticsplus==0.0.28 ultralytics==8.0.43
```
### Summon the model and unveil its secrets:
### Wave your wand (or keyboard) to get started!
```
from ultralyticsplus import YOLO, render_result
import cv2
```
### Cast a spell to summon the model
```
model = YOLO('foduucom/shelf-object-detection-yolov8')
```
### Tweak the magical parameters
```
model.overrides['conf'] = 0.25  # NMS confidence threshold
model.overrides['iou'] = 0.45  # NMS IoU threshold
model.overrides['agnostic_nms'] = False  # NMS class-agnostic
model.overrides['max_det'] = 1000  # maximum number of detections per image
```
### set image
```
image = "path/to/your/shelf/image"

#you can pass live camera streaming or video
#Begin the mystical journey through video frames
#(Remember to have your retail tapestry ready)
while cap.isOpened():
    # Read a frame from the video
    success, frame = cap.read()

    if success:
        # Unleash the magic of YOLOv8
        results = model(frame)

        # Showcase the magic on the frame
        annotated_frame = results[0].plot()

        # Present the enchanted frame
        cv2.imshow("YOLOv8 Retail Wizardry", annotated_frame)

        # Dispel the spell if 'q' is pressed
        if cv2.waitKey(1) & 0xFF == ord("q"):
            break
    else:
        # Return to reality when the video ends
        break
```

### Release your captive video and close the portal
```
cap.release()
cv2.destroyAllWindows()
```

### Contact us
For inquiries and contributions, please contact us at - [info@foduu.com](mailto:info@foduu.com)
