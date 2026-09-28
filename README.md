# JW Calendar 2027 API

JW Calendar 2027 API provides one read-only JSON document with Gregorian calendar metadata for 2027. It includes year-level properties and the length and first weekday of each month.

**Official website:** [JW Calendar](https://jwcalendar.com/)

## Endpoint

`GET https://karencohenjw.github.io/jwcalendar-calendar-api/api/v1/year/2027.json`

The origin is a static JSON file. It accepts no query parameters or request body.

## Example request

```bash
curl --fail --silent --show-error \
  'https://karencohenjw.github.io/jwcalendar-calendar-api/api/v1/year/2027.json'
```

## Response fields

| Field | Type | Description |
| --- | --- | --- |
| `api` | string | API name. |
| `version` | string | Dataset API version. |
| `year` | integer | Gregorian year represented by the response. |
| `calendar` | string | Calendar system used by the dataset. |
| `leap_year` | boolean | Whether the year is a leap year. |
| `website` | string | Link to JW Calendar. |
| `months` | array | Twelve records, ordered January through December. |

Each month record contains `number`, `name`, `days`, and `first_weekday`. Weekday names use English names from Monday through Sunday as applicable.

## Example integration

```javascript
const url = "https://karencohenjw.github.io/jwcalendar-calendar-api/api/v1/year/2027.json";
const response = await fetch(url);
if (!response.ok) throw new Error(`Calendar request failed: ${response.status}`);
const calendar2027 = await response.json();
console.log(calendar2027.months[0]);
```

## Scope

This endpoint contains Gregorian year and month metadata for 2027. It does not provide holidays, time-zone conversions, event schedules, or data for other years. The origin file is public and read-only.

## About JW Calendar

The API is associated with [JW Calendar](https://jwcalendar.com/), which publishes printable calendar views and date-planning resources.
