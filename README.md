# Face-Masking-model-on-Google-Colab

import cv2
#load cascade
face_cascade= cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
#upload input image
img= cv2.imread('rakshuuu.jpg')
#detect faces
faces=face_cascade.detectMultiScale(img,1.1,4)
#draw rectangle around faces, taking pic to 4D level, xywh are dimensions, 255 is defined for format for calling the whole picture
#255,0,0 means call whole pic if it was(255,89,56) then it means call                                                                                         
for(x,y,w,h) in faces:
  cv2.rectangle(img,(x,y),(x+w,y+h),(255,0,0),2)
#export image
cv2.imwrite("face_detected.png",img)
print('photo successfully exported')
