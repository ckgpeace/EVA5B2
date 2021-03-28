Train YoloV3 on custom data set:

1. Data Annotation with  https://github.com/miki998/YoloV3_Annotation_Tool
2. Follow the instructions in https://github.com/theschoolofai/YoloV3
3. Inference on custom data after set with following steps:
    1. Download a very small (~10-30sec) video from youtube which shows your classes. 
    2. Use ffmpeg to extract frames from the video. 
    3. Upload on your drive (alternatively you could be doing all of this on your drive to save upload time)
    4. Infer on these images using detect.py file. **Modify** detect.py file if your file names do not match the ones mentioned on GitHub. 
    5. python detect.py --conf-thres 0.3 --output output_folder_name
    6. Use ffmpeg  to convert the files in your output folder to video
    7. Upload the video to YouTube.

4. Link to my infered video: https://www.youtube.com/watch?v=WoBlyFmzISo

Thanks
