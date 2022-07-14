# Your next Add-to-Calendar Button

![Add-to-Calendar Button](https://github.com/jekuer/add-to-calendar-button/blob/main/img/repo_image.png?raw=true)

A convenient JavaScript snippet (VanillaJS, React, Angular, ...), which lets you create beautiful buttons, where people can add events to their calendars.

[![#1 Product of the Day on ProductHunt](https://api.producthunt.com/widgets/embed-image/v1/top-post-badge.svg?post_id=319458&theme=dark&period=daily)](https://www.producthunt.com/products/add-to-calendar-button-generator)

[![Code Quality](https://img.shields.io/codacy/grade/5c7c0bac087c4dfdb0669e8284f0459a/main?style=for-the-badge)](https://app.codacy.com/gh/jekuer/add-to-calendar-button/dashboard)
[![Build Status](https://img.shields.io/github/workflow/status/jekuer/add-to-calendar-button/Node.js%20Package?style=for-the-badge)](https://github.com/jekuer/add-to-calendar-button/actions/workflows/npm-publish.yml)
[![npm Installations](https://img.shields.io/npm/dt/add-to-calendar-button?label=npm%20Installations&style=for-the-badge)](https://www.npmjs.com/package/add-to-calendar-button)
[![jsDelivr npm Hits](https://img.shields.io/jsdelivr/npm/hm/add-to-calendar-button?label=jsDelivr%20npm%20hits&style=for-the-badge)](https://www.jsdelivr.com/package/npm/add-to-calendar-button)

<br /><br />

## 👇 Use case // Who this is for

This is for everybody, who wants to include a button at his/her website or app, which enables users to easily add a specific event to their calendars.
It's main goal is to keep this process as easy as possible at maximum compatibility. Simply define your button configuration and everything else is automatically generated by the script.
Supporting calendars at Apple, Google, Microsoft (365, Outlook, Teams), Yahoo, and generic iCal.

![Supported Calendars](https://github.com/jekuer/add-to-calendar-button/blob/v1.11/img/badge-supported-calendars.svg)

The script integrates easily with any usual HTML webpage (**VanillaJS** way) as well as popular JavaScript frameworks and libraries like **Angular**, **React**, **Vue**, **Svelte**, and more.

![Supported Technology](https://github.com/jekuer/add-to-calendar-button/blob/v1.11/img/badge-technology.svg)

In terms of system support, **all modern browsers** (Chrome, Edge, Firefox, Safari) on **Windows, Mac, Android, and iOS** as well as rather restricted environments like the **Instagram** in-app browser are supported.

![Supported Systems](https://github.com/jekuer/add-to-calendar-button/blob/v1.11/img/badge-supported-systems.svg)

<br /><br />

## ▶️ Demo

See [jekuer.github.io/add-to-calendar-button](https://jekuer.github.io/add-to-calendar-button/) for a live demo.

And remember to ⭐**star** this repository in order to save it for later! 🤗

<br /><br />

## ✨ Features

- Simple and convenient integration of multiple buttons, configurable directly within the HTML code.
- Optimized and adjustable UX (for desktop and mobile).
- Beautiful UI (the best combined from experts around the world).
- Up-to-date integration of all popular calendars:
  - **Google** Calendar.
  - **Yahoo** Calender.
  - **Microsoft 365, Outlook, and Teams**.
  - Automatically generated **iCal/ics** files (for all other calendars, like **Apple**).
- Timed and all-day events.
- Recurring events (where supported by the calendar)
- Translatable labels and dynamic dates.
- Dynamic dates and timezone.
- Auto-generated Schema.org rich (structured) data for better SEO.
- Full support for mouse, touch, or keyboard input.
- Well documented code, to easily understand the processes and build on top of it.

![Demo Screenshot](https://github.com/jekuer/add-to-calendar-button/blob/main/img/demo.gif?raw=true)

<br />

---

<br />

## 📦 Installation / Setup

### Option 1: simple (self-hosted)

1.  Check whether you are looking at the original and therefore up-to-date code at [github.com/jekuer/add-to-calendar-button](https://github.com/jekuer/add-to-calendar-button).
2.  **Download** the code directly from GitHub **or clone** the git repository.
3.  Copy the css (atcb.min.css) and js (atcb.min.js) files from the assets (not the "npm_dist") folders.
4.  Include those files in your project. The css goes into the `<head>`, the js into the `<body>` footer.

### Option 2: simple (CDN)

Instead of downloading the files, you can use the jsDeliver CDN.
Put 
```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/add-to-calendar-button@1.10.1/assets/css/atcb.min.css">
```
into the `<head>` and 
```
<script src="https://cdn.jsdelivr.net/npm/add-to-calendar-button@1.10.1" defer></script>
``` 
into the `<body>` footer. 

Leave out the patch number at the version ("1.9" instead of "1.9.2") to automatically pull the latest patched version. See [jsDeliver.com](https://www.jsdelivr.com/features#npm) for more options.

### Option 3: npm
Import the package using the following npm command:
```
npm install add-to-calendar-button
```

Import the module into your project/component. For example with Angular/React: 
```
import { atcb_action, atcb_init } from 'add-to-calendar-button';
```

Either use `atcb_action` with your own buttons/forms/etc, or run `atcb_init` after the DOM has been loaded. To determine the right moment to execute, ...
    - with Angular, you would use `ngAfterViewInit()` with `atcb_init();` (mind that, depending on your app, other hooks might be better);
    - with React, you might want to include an event listener like `document.addEventListener('DOMContentLoaded', atcb_init, false);` or using hooks in a functional component like `useEffect(() => atcb_init());`

Include the css. For example with Angular or React, add `@import 'add-to-calendar-button/assets/css/atcb.min'` to some other css file - or include it in other more direct ways (like adding `import 'add-to-calendar-button/assets/css/atcb.css';` to the respective component).

<br />

## 🎛️ Configuration

A button can be easily created by placing a respective placeholder, wherever you want the button to appear.
(The `style="display:none;"` theoretically is not necessary, but should be used for better compatibility.)

```html
<div class="atcb" style="display:none;">(...)</div>
```

Within this placeholder, you can easily configure the button, by placing a respective JSON structure.
Mind that with Angular, you might need to escape the { with `{{ '{' }}` and } with `{{ '}' }}`; with React it would be `{ '{' }` and `{ '}' }`.

<br />

### Minimal structure (required)

Mind that for auto-generating rich snippets, a location would be mandatory as well.

```html
<div class="atcb" style="display:none;">
  {
    "name":"Add the title of your event",
    "startDate":"2022-02-21",
    "endDate":"2022-03-24",
    "options":[
      "Google"
    ]
  }
</div>
```

<br />

### Full structure

```html
<div class="atcb" style="display:none;">
  {
    "name":"Add the title of your event",
    "description":"A nice description does not hurt",
    "startDate":"2022-02-21",
    "endDate":"2022-03-24",
    "startTime":"10:13",
    "endTime":"17:57",
    "location":"Somewhere over the rainbow",
    "label":"Add to Calendar",
    "options":[
      "Apple",
      "Google",
      "iCal",
      "Microsoft365",
      "MicrosoftTeams",
      "Outlook.com",
      "Yahoo"
    ],
    "timeZone":"Europe/Berlin",
    "trigger":"click",
    "inline":"true",
    "listStyle":"modal",
    "iCalFileName":"Reminder-Event"
  }
</div>
```

<br />

### React examples

#### atcb_action

If you can't or don't want to use `atcb_init`, you can use the `atcb_action` import with your own buttons or other elements/components.

This may work better with React and other frontend frameworks, but it misses the Schema.org and button specific functionalities.

```js
import React from 'react';
import { atcb_action } from 'add-to-calendar-button';

const MyComponent = () => {
  const [name, setName] = React.useState("Some event");
  const changeName = e => {
    setName(e.target.value);
  };
  return (
    <form onSubmit={e => {
      e.preventDefault();
      atcb_action({
        name,
        startDate: "2022-10-14",
        endDate: "2022-10-18",
        options: ['Apple', 'Google', 'iCal', 'Microsoft365', 'Outlook.com', 'Yahoo'],
        timeZone: "Europe/Berlin",
        iCalFileName: "Reminder-Event",
      });
    }}>
      <input value={name} onChange={changeName} />
      <input type="submit" value="save" />
    </form>
  );
}
```

#### atcb_init

Alternatively, you could use `atcb_init` with a `useEffect` hook:

```js
import React from "react";
import { atcb_init } from "add-to-calendar-button";
import 'add-to-calendar-button/assets/css/atcb.css';

const MyComponent = () => {
  React.useEffect(atcb_init, []);
  return (
    <div className="atcb">
      { '{' }
        "name":"Add the title of your event",
        "description":"A nice description does not hurt",
        "startDate":"2022-02-21",
        "endDate":"2022-03-24",
        "startTime":"10:13",
        "endTime":"17:57",
        "location":"Somewhere over the rainbow",
        "label":"Add to Calendar",
        "options":[
          "Apple",
          "Google",
          "iCal",
          "Microsoft365",
          "Outlook.com",
          "Yahoo"
        ],
        "timeZone":"Europe/Berlin",
        "iCalFileName":"Reminder-Event"
      { '}' }
    </div>
  );
}
```

<br />

### Important information and hidden features

- The `label` is optional, but enables you to customize the button text. Default: "Add to Calendar".
- Dates need to be formatted as YYYY-MM-DD ([ISO-8601](https://en.wikipedia.org/wiki/ISO_8601)).
- You can also use the word `today` as date. It will then dynamically use the current day at click.
- Add `+5` at the end of the date to dynamically add 5 days (or any other number). `2022-01-30+12` would generate the 11th of February 2022. This can be interesting, when combined with `today`.
- Times need to be formatted as HH:MM.
- Times are optional. If not set, the button generates all-day events.
- 1 option is required. You can add as many as you want. The supported formats are listed above.
- If you want to rename (or translate) a label, use the following schema at the options: optionName + Pipe + yourLabel. "Google|Google Kalender" would generate a Google Calendar option, but label it as "Google Kalender".
- You can and should add a `timeZone` (TZ name). Find a list of them at [Wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).
- Alternatively, you can set the `timeZoneOffset`, which will always override the `timeZone`. If neither of them is set, the date refers to UTC time.
- The `timeZone` option is recommended since it considers things like summer/winter time, but might not work in very old browsers. `timeZoneOffset` works with older browsers, but is quite static.
- Use "currentBrowser" as value for `timeZone` to dynamically use the time of the user's browser. Use this with caution, since it would mean that the date and time will differ per user, which should not be the usual case! (Requires all times to be set.)
- Use "recurrence" to define recurring events. Use can use any **valid** [RRULE](https://www.rfc-editor.org/rfc/rfc5545) to define the respective rule ([click here](https://icalendar.org/rrule-tool.html) for a generator). But mind that this will deactivate the Yahoo, Microsoft365, Teams, and Outlook options, since they do not support it at the moment (users could still use iCal in this case).
- You can set the `trigger` to `click`. This makes the button open on click at desktop. Otherwise, the default would be to open on hover. On touch devices, this makes no difference.
- If you want to define a specific name for any generated ics file (iCal), you can specify it via the `iCalFileName` option. The default would be "event-to-save-in-my-calendar".
- ics files are generated on the fly. However, if you want to go more stable, you can also explicitly define a self-hosted file, setting its path with the `icsFile` option.
- You can use the option `"inline":true` in order to make the button appear with inline-block instead of block style.
- The default style for the options list, using the regular button, would be a dropdown. You can set the option `listStyle` to "modal" in order to force the modal version (this would also force the click trigger).
- Formatting a URL in the description like `[url]https://....[/url]` makes it clickable. `[url]https://....|URL Text[/url]` defines a linked textblock saying "URL Text" (not supported by Apple, iCal, and Yahoo; not supporting special characters).
- If you require line breaks within the description, use `\n` or `<br>`.
- If you set at least a name, startDate, and location, the script automatically generates schema.org rich data. Use a URL for the location and it will be labeled as online event.
- Each generated button and option has a speaking id to be used for any tracking methods. Scheme: "atcb-btn-_IDENTIFIER_" or "atcb-btn-_IDENTIFIER_-google" (for the Google option) respectively. The _IDENTIFIER_ will be an automatic number, but can be overridden by providing the option `"identifier":"xyz"` (no special characters allowed; needs to be unique).

<br />

---

<br />

## 🙌 Contributing

Anyone is welcome to contribute, but mind the [guidelines](.github/CONTRIBUTING.md):

- [Bug reports](.github/CONTRIBUTING.md#bugs)
- [Feature requests](.github/CONTRIBUTING.md#features)
- [Pull requests](.github/CONTRIBUTING.md#pull-requests)

**IMPORTANT NOTE:** Run `npm install`, `npm format`, and `npm run build` to auto-lint, create the minified js and css files, its sourcemap files as well as the npm_dist/ folder and content!

<br />

## ⚡ Changelog

Find all changes in the dedicated file at [CHANGELOG.md](CHANGELOG.md).

<br />

## 💜 Kudos go to

- [uxwing.com](https://uxwing.com)
- [Chad Ostrowski (chadoh)](https://github.com/chadoh)
- ... and all other contributors!

<br />

## 📃 Copyright and License

Copyright (c) [Jens Kuerschner](https://jenskuerschner.de).

Licensed under [MIT license (with “Commons Clause” License Condition v1.0)](LICENSE.txt).

<br />

---

<br />

## 🔎 Why this repo exists

While building a personal wedding page, I was confronted with the task to include a button, where invited people could save the event to their calendars.
I did not want to build this from scratch (first) and therefore started the usual web research.
Unfortunately, all I found where some extremely outdated code snippets, which did not really fit all the modern systems and calendar tools.
Beside that, there was only the solution by AddEvent.com - all over the place. I was looking at CodePen and all I found where thousands of pens, which basically only included the AddEvent tool.

The problems with AddEvent.com:

- it holds tons of features, which I did not need. They make sense for companies, but not for most personal projects.
- it limits the free tier to 50 event adds per month (consider the wedding case - this is way too less - they upgraded that in the meantime, but still).
- it brings some data privacy issues, since you basically send your users to their not really data secured service. GDPR alert!
- the UX/UI is not ideal (imho).

**Bottom line:** Paying for features, which I did not need - at additional privacy concerns - that made me create this solution (for you).

<br />
