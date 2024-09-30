# Lego's Custom Reporting Marks

This mod adds the ability to force certain cars to have certain reporting marks. It uses a .json file to specify what identifiers get what reporting marks.

# HOWTO

To add custom reporting marks, make or use an existing UMM mod, and add a new folder inside of it called `CustomReportingMarks`. Inside of that folder, create a new file called `ReportingMarks.json`.

## JSON SETUP

```json
[
    {
        "identifier": null,
        "reportingMarks": [
            "test1",
            "test2"
        ]
    },
    {
        "identifier": null,
        "reportingMarks": [
            "test3",
            "test4"
        ]
    }
]
```

## identifier

The car's identifier you want to force a reporting mark on.

## reportingMarks

A list of reporting marks that will be randomly chosen from for the specified car.
