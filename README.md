# Vue - Notification Project

![bandicam-2022-10-17-15-17-04-425](https://user-images.githubusercontent.com/72731296/196175476-4c88b5cb-31f6-499b-86ee-95abb0fe2ed2.gif)

## Usage

```bash
import { ref } from "vue";
import NotificationsList from "./components/Notification/NotificationList.vue";
import { toast } from "./components/Notification/Toastify.js";
```

```bash
const notifications = ref([]);

notifications.value.push(toast())

<template>
	<div>
		<NotificationsList :notifications="notifications"></NotificationsList>
	</div>
</template>
```

## Creating a Notification

### Custom Notification

```bash
notifications.value.push(toast("This is a custom notification", {
	position : "top-center"
	icon: "😉",
	background : "#fafafa",
	color: "#000",
	duration : 6000,
	barBackground : "red",
	}))
```

### Success Notification

```bash
notifications.value.push(toast().success("Success Notification Message"))
```

### Error Notification

```bash
notifications.value.push(toast().error("Error notification",{
	position : "bottom-right"
	icon : "🤬",
	duration : 5000,
	background : "red"
	color : "black"
	barActive : false
}))
```

### Warning Notification

```bash
notifications.value.push(toast().warning())
```

### Info Notification

```bash
notifications.value.push(toast().info())
```

### Props

| Prop          | Type    | Default         |
| ------------- | ------- | --------------- |
| description   | String  | Default Message |
| position      | String  | 'top-right'     |
| icon          | String  | 'mood'          |
| duration      | Number  | 10000           |
| background    | String  | 'black'         |
| barBackground | String  | 'gray'          |
| barActive     | Boolean | true            |
| color         | String  | 'white'         |

<br/>
