# posedetector-in-human
i am Human Pose Estimation (HPE) is a way of identifying and classifying the joints in the human body. Essentially it is a way to capture a set of coordinates for each joint (arm, head, torso, etc.,) which is known as a key point that can describe a pose of a person. The connection between these points is known as a pair.


import cvzone
import cv2
import os
from cvzone.PoseModule import PoseDetector


cap = cv2.VideoCapture("4.mp4.mp4")
detector = PoseDetector()




while True:
    success, img = cap.read()
    img = detector.findPose(img)
    lmList, bboxInfo = detector.findPosition(img, bboxWithHands=False,draw=False)
    if lmList:
          center = bboxInfo["center"]


    cv2.imshow("Image", img)
    cv2.waitKey(1)
