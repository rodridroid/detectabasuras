from imageai.Detection import ObjectDetection
import webbrowser
url = 'https://www.youtube.com/watch?v=VwAC55fIwTg'


# Instantiating the object detection class
detector = ObjectDetection()

# Setting a path to the YOLOv3 model
model_path = "/content/yolov3.pt"

# Installing the YOLOv3 model and setting a path to the weights file
detector.setModelTypeAsYOLOv3()
detector.setModelPath(model_path)

# Loading the model
detector.loadModel()

def detect_objects_on_road(input_image, output_image, model_path):
    detector = ObjectDetection()
    detector.setModelTypeAsYOLOv3()
    detector.setModelPath(model_path)
    detector.loadModel()
    detections = detector.detectObjectsFromImage(
        input_image=input_image,
        output_image_path=output_image,
        minimum_percentage_probability=30
    )
    return detections

def analyze_objects(detections):
    road_objects = []
    if len(detections) > 0:
      for detection in detections:
          if detection["name"] in ["bottle", "banana", "vase","pottedplant", 'mouse','cell_phone','wine_glass','apple','cup']:
              road_objects.append(detection)
    return road_objects

def road_safety_rules():
    print()
    print("Hola, soy ReciclaTú, el Dectector de basuras")
    print("Identificación de Plasticos")
    print("Identificación de Residuos")
    print("Monitoreo de cascara de frutas")
    print("Detección de Papeles y cartones Invasores")
    print("Ah, y no te olvides seguir a Desecha2  pd: Ese canal no esta asociado ni relacionado con el proyecto")
    print("ppd:este es el link el canal https://www.youtube.com/@mayorita55 porque hay otro canal con el mismo nombre")


input_image= "images.jpg"
output_image = "output_image.jpeg"
detections = detect_objects_on_road(input_image, output_image, "/content/yolov3.pt")
road_objects = analyze_objects(detections)
if len(road_objects) > 0:
  print("Basura Detectada")
  print("consejos para reciclar:https://www.youtube.com/watch?v=VwAC55fIwTg")
  webbrowser.open_new(url)
  for obj in road_objects:
      print(obj["name"], " : ", obj["percentage_probability"], " : ", obj["box_points"])
else:
   print("No se detecta basura")
road_safety_rules()
