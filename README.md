google-analytics-universal-tracker
==================================

`google-analytics-universal-tracker` is a Polymer Element for Google Analytics Universal tracker, supports page and event tracking

## Getting Started

### Installation
```bash
bower install google-analytics-universal-tracker --save
```
###Usage
####Initialise

```html
<link rel="import" href="bower_components/google-analytics-universal-tracker/google-analytics-universal-tracker.html">
<!--...-->
<google-analytics-universal-tracker code="UA-XXXXXXX-x" auto></google-analytics-universal-tracker>
```	

If you are using regular anchor links and not push-state links you are ready to go! 
If you have a Single Page Application that uses push-state, eg with `page.js` or `<app-router>` you will need to signal to the `google-analytics-tracker` element that the page has changed. 
The Page Change events are handled using iron-signals so you do not need to do any dom finding to trigger a page track.

####Track a page Change
```javascript
    this.fire('iron-signal', {name: 'track-page', data: { path: "/about.html" } });	
```
####Track an Event
```javascript
    this.fire('iron-signal', {name: 'track-event',data: {category: "messages",action: "send_text_message",label: "group",value: 1}});
```
####User id attribution
To use [Google Analytics user id attribution](https://developers.google.com/analytics/devguides/collection/analyticsjs/user-id) set the user id property on the element:
```javascript
    document.querySelector("google-analytics-universal-tracker").userId = loggedInUserId;
```
