# aiproject
CFAI Buildpack: Example Cloud Foundry Artificial Intelligence Project
    A Hackathon Project at the Cloud Foundry Summit 2019 The Hague  
Copyright (c) 2019 DanielWunder, MauriceBrinkmann, SebestyenMiklos  
Demo for and depending on the aibuildpack: https://github.com/mauricebrinkmann/aibuildpack
  
## Usage
```BASH
git clone https://github.com/mauricebrinkmann/aiproject.git
cd aiproject
cf push
```

## Test  
  
Assuming that ai.example.com will be the route to the previously pushed AI project using this aibuildpack:
```BASH
# Check the model to equal the ai.json from this project
curl https://ai.example.com/model

# Check the model by predicting some values
curl -X POST -d '{ "input 1": [ 1, 2, 3 ], "input 2": [ 0.4, 0.5, 0.6 ] }' https://ai.example.com
```
Returns:  
```JSON
{
    "prediction": [
        9.999999999999957,
        19.999999999999975,
        29.999999999999996
    ]
}
```
   
```BASH
# Check the model by predicting some other values
curl -X POST -d '{ "input 1": [ 1.5, 3 ], "input 2": [ 0.5, 0.7 ] }' https://ai.example.com
```
Returns:  
```JSON
{
    "prediction": [
        14.999999999999973,
        30.000000000000007
    ]
}
```
