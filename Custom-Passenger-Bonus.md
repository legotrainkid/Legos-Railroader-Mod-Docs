# Lego's Custom Passenger Bonus

To add a bonus to a car or locomotive, you need to add the component to the component section in the items definition

## COMPONENT JSON
```
{
  ﻿"kind": "CustomBonus",
  ﻿"bonusAmount": 1.0,
  ﻿"minNumOfCars": 0,
  ﻿"maxNumOfCars": 0,
  ﻿"startHour": 0.0,
  ﻿"endHour": 24.0,
  ﻿"minimumOfCartype": 0,
  ﻿"maximumOfCartype": 0,
}
```

## bonusAmount
A decimal percentage for the amount to increase or decease the fares by (1.0 is 100%, or unchanged, 0.9 is 90% of the fares, 1.1 is 110%, etc.)

## min/maxNumOfCars
The number of cars that must be on the consist. Includes locomotives and tenders. A 0 in the max means no maximum amount

## start/endHour:
The hours between which the bonus will be applied. (0 - midnight)

## minimum/maximumOfCarType
The number of this car required on the train for the bonus to be applied. A 0 in the max means no maximum amount
