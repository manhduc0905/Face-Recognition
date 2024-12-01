
### General Structure
The project will have several directories, as follows:

* `dataset`: contains images of people (each person is placed in a separate folder). In practice, it is advisable to include IDs for each person to avoid issues in case multiple people share the same name.
* `test_images`: contains images for testing (not overlapping with the dataset).
* `output`: stores the video after face recognition processing.
* `videos`: input video files.
Additional files such as:
* `build_dataset.py`: used to build the dataset.
* `encode_faces.py`: encodes (128-dimensional vectors) for faces.
* `recognizer_faces_image.py`: performs face recognition from images based on the dataset's encodings. Note that in this file, there is a part where the match is checked (matches = face_recognition.compare_faces(data["encodings"], encoding, 0.4)), and we can adjust the last parameter if there are incorrect matches (e.g., an image not in the dataset being incorrectly recognized).
* `recognizer_faces_video.py`: performs face recognition from a webcam video. This code can be slightly modified to handle videos from files.
* `encoding.pickle`: stores the encodings created by encode_faces.py to disk.
### Sources
1. https://github.com/ageitgey/face_recognition/blob/master/face_recognition/api.py#L213
2. https://www.pyimagesearch.com/2018/06/18/face-recognition-with-opencv-python-and-deep-learning/