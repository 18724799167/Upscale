# Upscale

**Argument**

img_dir:path to folder containing pictures

img_type:image format，default is "png"

output_dir:the result path

device_index: gpu id, default is "0"

model_type: cnn or gan, defalut is "cnn"

python3.6 main.py --img_dir=path_to_img --output_dir=path_to_result --model_type=cnn
--------

the tutorial of upscaling images in your GPU server
##Step1
pull docker image
`dokcer pull registry.cn-hangzhou.aliyuncs.com/rotoscope/upscale:v1.0`
before that you need to have this permission. We have done at 192.168.2.150

##Step2
run doccker
`docker run -dit -v /data/upscale:/data --name upscale registry.cn-hangzhou.aliyuncs.com/rotoscope/upscale:v1.0`
the dir `/data/upscale` is your host path. We have done at 192.168.2.150

##Step3
prepare your images,
make a dir in /data/upscale at your host server. such as `apple`, ad  `apple/result`.

Then, run 
 `docker exec -it upscale python3.6 main.py --img_dir=/data/apple--output_dir=/data/apple/result --model_type=cnn --img_type=jpg`
 
 - img_type: your image ext, jpg or png
 - img_dir: your image(s) path
 - output_dir: the result of your image(s) path
