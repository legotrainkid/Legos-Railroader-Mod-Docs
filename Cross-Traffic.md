# Lego's Cross Traffic

To add your own car/load combinations, either edit the file in `your_path_to_mod/CrossTrafficLoads/CarLoads.json `, or make a mod that adds more. To make a mod, download the [Example Mod](https://www.nexusmods.com/Core/Libs/Common/Widgets/ModRequirementsPopUp?id=834&game_id=5982) package, and edit the info.json to give your mod a custom ID and author. Then, edit the `CrossTrafficLoads/CarLoads.json` file to add whatever car and load combinations you want!

If you want to add a crosstraffic load to an existing mod, simply add `legotrainman.crosstraffic` to your mod's requirements, then create a folder called `CrossTrafficLoads`, with the `CarLoads.json` file inside it.

Example Json
```
[
  {
  "carType": "ARR CAR CODE (EG, FM* for any flat car, HMR for a covered hopper",
    "loads": [
      "LOAD ID",
      "LOAD ID"
    ]
  },
  {
    "carType": "ARR CAR CODE (EG, FM* for any flat car, HMR for a covered hopper",
    "loads": [
      "LOAD ID",
      "LOAD ID"
    ]
  },
]
```
