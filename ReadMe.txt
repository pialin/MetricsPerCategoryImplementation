Implemetation of "include_metrics_per_category" and "all_metrics_per_category" option in "eval_config" of tensorflow object detection api.Three code additions are listed below:
1.addtion in "cocoapi/PythonAPI/pycocotools/cocoeval.py":from line 499 to line 650
2.addtion in "models/research/object_detetcion/metrics/coco_tools.py":from line 239 to line 240
3.add
{
  metrics_set: "coco_detection_metrics" 
  include_metrics_per_category: true 
  all_metrics_per_category: true #optional, set it true if you want more metrics detail
}
to "eval_config" part in pipeline config file.

The code changes are only tested in my code to train a "fastrcnn_resnet_101" model. You should see per category metrics stats in tensorboard if they work. Any feedback would be appreciated.
