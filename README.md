![Add to Calendar Button](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/readme-header.png?raw=true)

[![Code Quality](https://img.shields.io/codacy/grade/572c0a102d7b4f39b792439dcd2e8aad/main?style=for-the-badge)](https://app.codacy.com/gh/add2cal/add-to-calendar-button/dashboard)
[![Build Status](https://img.shields.io/github/workflow/status/add2cal/add-to-calendar-button/Node.js%20Package?style=for-the-badge)](https://github.com/add2cal/add-to-calendar-button/actions/workflows/npm-publish.yml)
[![npm Installations](https://img.shields.io/npm/dt/add-to-calendar-button?label=npm%20Installations&style=for-the-badge)](https://www.npmjs.com/package/add-to-calendar-button)
[![jsDelivr npm Hits](https://img.shields.io/jsdelivr/npm/hm/add-to-calendar-button?label=jsDelivr%20npm%20hits&style=for-the-badge)](https://www.jsdelivr.com/package/npm/add-to-calendar-button)

<br />

# Your next Add to Calendar Button

The convenient JavaScript snippet, which lets you reliably create beautiful buttons, where people can add events to their calendars.

[![#1 Product of the Day on ProductHunt](https://api.producthunt.com/widgets/embed-image/v1/top-post-badge.svg?post_id=319458&theme=dark&period=daily)](https://www.producthunt.com/products/add-to-calendar-button-generator)

<br /><br />

For everybody, who wants to include a button at his/her website or app, which enables users to easily add a specific event to their calendars.
It's main goal is to keep this process as easy as possible at maximum compatibility. Simply define your button configuration and everything else is automatically generated by the script.
Supporting calendars at Apple, Google, Microsoft (365, Outlook, Teams), Yahoo, and generic iCal.

![Supported Calendars: Apple (via iCal), Google, Microsoft (365, Outlook, Teams), Yahoo, generic iCal](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/badge-supported-calendars.svg)

The script integrates easily with any usual HTML webpage (**VanillaJS** way) as well as popular JavaScript frameworks and libraries like **Angular**, **React**, **Vue**, **Svelte**, and more.

![Supported Technology: Angular, React, Vue, Svelte, and every other project that can load JavaScript](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/badge-technology.svg)

In terms of system support, **all modern browsers** (Chrome, Edge, Firefox, Safari) on **Windows, Mac, Android, and iOS** as well as rather restricted webview environments like the **Instagram** in-app browser are supported.

<br /><br />

---

<br />

## ▶️ Demo

See [add-to-calendar-button.com](https://add-to-calendar-button.com/) for a live demo.

And remember to [⭐ **star** this repository](#) in order to stay up-to-date and save it for later! 🤗

[![Remember to star this repository!](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/starring.gif?raw=true)](#)

## ✨ Features

Simple and convenient integration of 1 or many buttons, configurable directly within the HTML code.

### Supported Calendars

- **Google** Calendar.
- **Yahoo** Calender.
- **Microsoft 365, Outlook, and Teams**.
- Automatically generated **iCal/ics** files (for all other calendars, like **Apple**).

### Event Types

- Timed and all-day events.
- One-time, recurring, or fluid.
- Most robust time zone and daylight saving management (via our own [TimeZones iCal Library](https://github.com/add2cal/timezones-ical-library)).
- Dynamic dates (like "today + 3").

### Look

- Beautiful and adjustable UI.
- Light and dark mode.
- Multiple themes.

### Accessibility

- Optimized and adjustable UX (for desktop and mobile).
- Dynamic dropdown positioning.
- Taking care of all those edge cases, where some scenarios do not support specific setups (like WebView blocking downloads); utilizing beautiful user guidance workarounds.
- Auto-generated Schema.org rich (structured) data for better SEO.
- Full support for mouse, touch, or keyboard input (W3C WAI compliant).
- Supporting 20+ languages, incl. RTL text for Arabic; but also custom labels and text blocks.

### And much more

- Well documented code, to easily understand the processes and build on top of it.
- No external module or backend dependencies.
- Therefore, fully GDPR, CCPA, and LGPD compliant - without the need of signing some data processing agreement.
- FREE and open source.

![Demo Screenshot](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/demo.gif?raw=true)

<br />

---

<br />

## 📦 Installation / Setup

### Option 1: simple (CDN)

You can use the jsDeliver CDN and load the respective ressources into your web project.

Put the css (use atcb-3d for an alternative style) into the `<head>`:

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/add-to-calendar-button@1/assets/css/atcb.min.css">
```

... and the javascript into the `<body>` footer:

```
<script src="https://cdn.jsdelivr.net/npm/add-to-calendar-button@1" async defer></script>
```

_Mind that this always pulls the latest release of v1! You can pin a more specific version by adding the exact version number after the "@" - see [jsDeliver.com](https://www.jsdelivr.com/features#npm) for details._
If you want to rather host it yourself, you could also download the source files or clone the repository (mind to take the original one at [github.com/add2cal/add-to-calendar-button](https://github.com/add2cal/add-to-calendar-button)) and maintain/update it manually.

<br />

### Option 2: npm

Import the package using the following npm command:

```
npm install add-to-calendar-button
```

Import the module into your project/component. For example with Angular/React:

```
import { atcb_action, atcb_init } from 'add-to-calendar-button';
```

Either use `atcb_action` with your own buttons/forms/etc, or run `atcb_init` after the DOM has been loaded. To determine the right moment to execute the `atcb_init`, ...

- with Angular, you would use `ngAfterViewInit()` with `atcb_init();` (mind that, depending on your app, other hooks might be better);
- with React, you might want to include an event listener for `DOMContentLoaded` or use a hook in a functional component like `useEffect(() => atcb_init());`.

Include the css. For example with Angular or React, add `@import 'add-to-calendar-button/assets/css/atcb.css'` to some other css file - or include it in other more direct ways (like adding `import 'add-to-calendar-button/assets/css/atcb.css';` to the respective component) (use atcb-3d for an alternative style).

<br /><br />

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

If there is no endDate set, the script assumes that it is the same as startDate.

Mind that for auto-generating rich snippets, a location would be mandatory as well. Even a timezone is not required, but recommended - if not given, the script will assume UTC.

```html
<div class="atcb" style="display:none;">
  {
    "name":"Add the title of your event",
    "startDate":"2022-02-21",
    "options":[
      "Google"
    ]
  }
</div>
```

<br />

### Full structure

_(More hidden options are described further below.)_

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
    "inline":true,
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

<br /><br />

### Important information and hidden features

- The `label` is optional, but enables you to customize the button text. Default: "Add to Calendar".
- Dates need to be formatted as YYYY-MM-DD ([ISO-8601](https://en.wikipedia.org/wiki/ISO_8601)).
- You can also use the word `today` as date. It will then dynamically use the current day at click.
- Add `+5` at the end of the date to dynamically add 5 days (or any other number). `2022-01-30+12` would generate the 11th of February 2022. This can be interesting, when combined with `today`.
- Times are optional. If not set, the button generates all-day events. If set, they need to be formatted as HH:MM
- You can and should add a `timeZone` (TZ name). Find a list of them at [Wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).
- Use "currentBrowser" as value for `timeZone` to dynamically use the time of the user's browser. Use this with caution, since it would mean that the date and time will differ per user, which should not be the usual case! (Requires all times to be set.)
- Use the `recurrence` option to define recurring events. But mind that this will deactivate the Yahoo, Microsoft365, Teams, and Outlook options, since they do not support it at the moment (users could still use iCal in this case).
  - You can use any **valid** [RRULE](https://www.rfc-editor.org/rfc/rfc5545) to define the respective rule ([click here](https://icalendar.org/rrule-tool.html) for a generator).
  - Or you define one of the following more simple rules: daily, weekly, monthly, yearly. If you go that way, you can enrich your rule with one of the following specifics:
    - `recurrence_interval` to specify the interval between iterations. "1" would be the default, while "3" would mean "every third".
    - `recurrence_until` to specify an end date. This should be the last day of the event, formatted as YYYY-MM-DD. Mind that this does not work in many applications! Rather use the count option.
    - `recurrence_count` to specify an upper limit of repetitions. If endDate and count are given, whatever comes first overrides the other. If none are given, it would repeat indefinitely.
    - `recurrence_byDay` to specify the weekdays (MO, TU, WE, TH, FR, SA, SU), where the even occurs (if, for example, it is bound to Tuesday instead of the 24th). Requires a weekly frequency. Can be enriched with a number to specify something like the 3rd Monday (3MO). Can be multiple, comma separated.
    - `recurrence_byMonthDay` to specify a numbered day (1, 2, ... 31) instead of a weekday. Requires a monthly frequency. Can be multiple, comma separated.
    - `recurrence_byMonth` to specify the months (1, 2, 3, ... 12), where the event should happen. Requires a yearly frequency. Can be multiple, comma separated.
  - Mind that the startDate needs to be valid within the given recurrence ruleset!
- If you want to rename a label, use the following schema at the options: optionName + Pipe + yourLabel. "Google|Google Kalender" would generate a Google Calendar option, but label it as "Google Kalender".
- There is almost no static text block. For the tiny little rest, you can define a translation by using the `language` option. Supported options and therefore languages: English (en, default), German (de), Dutch (nl), French (fr), Spanish (es), Portugese (pt), Turkish (tr), Chinese (zh), Arabic (ar, incl RTL).
- In case you want to customize them, you can alternatively set the option `customLabels` and provide a JSON object where the key would be the text block's identifier (lower case without spaces). See the bottom of the js file for possible text blocks. You can use HTML pseudo tags, which get transformed automatically (but not for styled labels). Suported ones: [url] (see next point), [br], [hr], [p], [strong], [u], [i], [em], [li], [ul], [ol], [h*] (like h1, h2, h3, ...).
- Formatting a URL in the description like `[url]https://....[/url]` makes it clickable. `[url]https://....|URL Text[/url]` defines a linked textblock saying "URL Text" (not supported by Apple, iCal, and Yahoo; not supporting special characters).
- You can set the `trigger` to `click`. This makes the button open on click at desktop. Otherwise, the default would be to open on hover. On touch devices, this makes no difference.
- If you want to define a specific name for any generated ics file (iCal), you can specify it via the `iCalFileName` option. The default would be "event-to-save-in-my-calendar".
- ics files are generated on the fly. However, if you want to go more stable, you can also explicitly define a self-hosted file, setting its absolute path with the `icsFile` option. Mind that the custom file name would not work in that case.
- You can use the option `"inline":true` in order to make the button appear with inline-block instead of block style.
- Change the relative size of the rendering by using hte option `size` with a value between 0 and 10 (default: 6, which equals 16px font-size).
- Use `"background":false` if you want to be the background overlay to be fully transparent.
- The default style for the options list, using the regular button, would be a dropdown. You can set the option `listStyle` to "modal" in order to force the modal version (this would also force the click trigger) or `overlay` to show the list right above the button. The default would also show the dropdown upwards, if this better fits the current viewport. You can block this behavior with the option `dropdown-static`.
- If you require line breaks within the description, use `\n` or `<br>`.
- If you set at least a name, startDate, and location, the script automatically generates schema.org rich data. Use a URL for the location and it will be labeled as online event.
- You can also define images to be set for the event's rich data. This needs to be an array. Define at least 1 image via an absolute url with at least 720px width. Recommended would be 3 images with a width of 1920px each. One with an aspect ration 1x1, one with 4x3, and one with 16x9. If not set, a default fallback image will be used.
- Each generated button and option has a speaking id to be used for any tracking methods. Scheme: "atcb-btn-_IDENTIFIER_" or "atcb-btn-_IDENTIFIER_-google" (for the Google option) respectively. The _IDENTIFIER_ will be an automatic number, but can be overridden by providing the option `"identifier":"xyz"` (no special characters allowed; needs to be unique).
- Each button comes with a dark and light mode. Set the option `lightMode` to "dark" or "light" explicitly, or use "system" to automatically adapt to the user's default setting. You can also use "bodyScheme" to look for the class "atcb-dark" at the body tag and connect the button dynamically to the style of your website.
- Optionally define an organizer for the event with the `organizer` option. Use the schema "NAME|EMAIL" (e.g. "John Doe|john.doe@gmail.com") and mind that this information will be public. Only supported by iCal at the moment.
- Theoretically, you can also use the options `uid`, `sequence`, `created`, `updated`, and `status` (TENTATIVE, CONFIRMED, CANCELLED) to override the default values and especially to manage event updates. Warning: You should only play with those settings, if you know what you are doing! This is also only supported by the iCal format (and even there not recognized by all calendars). To update an existing event, you would need to have a growing sequence number and also the organizer field (name and email) set.
- The default layout is more or less basic. You can use different style by loading different css files: atcb-3d.min.css, atcb-flat.min.css, and atcb-text.min.css are available.

<br />

---

<br />

## ⚡ Changelog

Find all changes in the dedicated file at [CHANGELOG.md](CHANGELOG.md).

<br />

## 🙌 Contributing

Anyone is welcome to contribute, but mind the [guidelines](.github/CONTRIBUTING.md):

- [Bug reports](.github/CONTRIBUTING.md#bugs)
- [Feature requests](.github/CONTRIBUTING.md#features)
- [Pull requests](.github/CONTRIBUTING.md#pull-requests)

**IMPORTANT NOTE:** Run `npm install`, `npm run format`, and `npm run build` to auto-lint and create the minified js, css, as well as its sourcemap files!

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
Beside that, there was only the solution by AddEvent.com - all over the place. I was looking at CodePen and all I found where thousands of pens, which basically only included the AddEvent tool, which is hardly connected to their paid services.

The problems with this and other solutions:

- It holds tons of features, which I did not need. They make sense for companies (also because a server-based solution is more reliable), but not for most small personal dev projects.
- It limited the free tier to 50 event adds per month (consider the wedding case - this is way too less).
- It brings some data privacy issues, since you basically send your users to their not fully data secured service. GDPR alert, if you do not inform people about this fact and the underlying Google services!
- I did not like the UX/UI.
- Other solutions where no longer up-to-date or have never been fully functional (there are so many edge cases).

**Bottom line:** Paying for features, which I did not need - at additional privacy concerns - that made me create this solution (for you).

**Fun fact:** AddEvent changed a lot in the meantime. They slightly increased the free tier and also published some code on GitHub (but still require their service and also not open source!). This might be cool for businesses, but a killer for smaller projects. Anyhow, it is moving into the right direction 😊.

<br />

---

<br />

## 💜 Kudos go to

[uxwing.com](https://uxwing.com) as well as all contributors:

<a href="https://github.com/jekuer"><img src="https://avatars.githubusercontent.com/u/8572883?v=4" title="jekuer" width="60" height="60"></a>
<a href="https://github.com/add-to-calendar"><img src="https://avatars.githubusercontent.com/u/110406429?s=96&v=4" title="add-to-calendar" width="60" height="60"></a>
<a href="https://github.com/chadoh"><img src="https://avatars.githubusercontent.com/u/221614?v=4" title="chadoh" width="60" height="60"></a>
<a href="https://github.com/bryan-brancotte"><img src="https://avatars.githubusercontent.com/u/11556772?v=4" title="bryan-brancotte" width="60" height="60"></a>
<a href="https://github.com/nticaric"><img src="https://avatars.githubusercontent.com/u/824840?v=4" title="nticaric" width="60" height="60"></a>
<a href="https://github.com/Ortovoxx"><img src="https://avatars.githubusercontent.com/u/56805259?v=4" title="Ortovoxx" width="60" height="60"></a>
<a href="https://github.com/emilebosch"><img src="https://avatars.githubusercontent.com/u/303135?v=4" title="emilebosch" width="60" height="60"></a>
<a href="https://github.com/killerrin"><img src="https://avatars.githubusercontent.com/u/3269687?v=4" title="killerrin" width="60" height="60"></a>
<a href="https://github.com/acm-will"><img src="https://avatars.githubusercontent.com/u/103984058?v=4" title="acm-will" width="60" height="60"></a>
<a href="https://github.com/ssaaiidd"><img src="https://avatars.githubusercontent.com/u/29234802?v=4" title="ssaaiidd" width="60" height="60"></a>
<a href="https://github.com/apps/dependabot"><img src="https://avatars.githubusercontent.com/in/29110?v=4" title="dependabot[bot]" width="60" height="60"></a>

<br />
