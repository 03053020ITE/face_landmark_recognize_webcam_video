# face_landmark_recognize_webcam_video
### 簡介
使用dlib人臉資料庫實作人臉定位、人臉特徵點座標標注以及人臉識別。我們能以此為基礎實作實時表情辨識；疲勞駕駛辨識；化妝卸妝系統；上班打卡系統等專案。
### 安裝
#### 從Ubuntu上安裝dlib人臉資料庫
```
sudo apt-get install build-essential cmake
```
```
sudo apt-get install libgtk-3-dev
```
```
sudo apt-get install libboost-all-dev
```
```
pip install dlib
```
#### 安裝人臉辨識模塊
```
pip3 install face_recognition
```
#### 若需 import face_recognition
```
pip install git+https://github.com/ageitgey/face_recognition_models
```
#### 基本程式碼範例 
圖片中定位人臉：
```
import face_recognition
image = face_recognition.load_image_file("your_file.jpg")
face_locations = face_recognition.face_locations(image)
```
圖片人臉特徵點座標標注：
![image](https://github.com/03053020ITE/face_landmark_recognize_webcam_video/blob/master/show/me3.PNG)
```
import face_recognition
image = face_recognition.load_image_file("your_file.jpg")
face_landmarks_list = face_recognition.face_landmarks(image)
```
#### 將圖片人臉進行化妝，可開發卸妝等專案
![image](https://github.com/03053020ITE/face_landmark_recognize_webcam_video/blob/master/show/makeup.PNG)
```
face_makeup.ipynb
```
#### 將影片中的人臉模糊，類似打馬賽克的效果
![image](https://github.com/03053020ITE/face_landmark_recognize_webcam_video/blob/master/show/blur.gif)
```
blur_face_video.ipynb
```
#### 影片、攝像頭人臉辨識
比對樣本圖片與影片、攝像頭所拍攝的人是否相同，並在人臉周圍畫上矩形框，人臉下方出現人名；並將每幀圖像縮小0.25倍來加速

![image](https://github.com/03053020ITE/face_landmark_recognize_webcam_video/blob/master/show/facerec.gif)
```
facerec_video.ipynb
```
```
facerec_webcam.ipynb
```
```
facerec_webcam_faster.ipynb
```
#### 找到圖片中的人臉
基於HOG的模型查找圖像中的所有人臉，這種方法相當準確，但不如CNN模型準確，也沒有GPU加速
```
find_faces_in_picture.ipynb
```
使用預先訓練的卷積神經網絡查找圖像中的所有人臉，方法比默認HOG模型更準確，但速度較慢
```
find_faces_in_picture_cnn.ipynb
```
#### 找到影片中的人臉
```
find_faces_in_picture_video.ipynb
```
#### 比對兩張人臉距離、人臉識別
通常不是檢查兩個人臉是否匹配（真或假），而是看看它們有多相似，模型的訓練方式是0.6或更小的距離應該匹配
```
face_disance.ipynb
```
```
recognize_faces_in_pictures.ipynb
```

