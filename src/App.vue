<script setup>
import {ref} from "vue";
import NotificationsList from "./components/Notification/NotificationList.vue";
import { toast } from "./components/Notification/Toastify.js";

const notifications = ref([]);

const clickHandler = () => {
	notifications.value.push(
		toast("This is a test notification", {
			icon: "🤞",
			duration: 5000,
			background: "#f0f0f0",
			color: "#212121",
			barBackground: "orange",
		})
	);
};

const successHandler = () => {
	notifications.value.push(
		toast().success())
};

const errorHandler = () => {
	notifications.value.push(
		toast().error())
};

const warningHandler = () => {
	notifications.value.push(
		toast().warning())
};

const infoHandler = () => {
	notifications.value.push(
		toast().info())
};
</script>

<template>
	<div class="btnGroups">
		<button class="showButton" @click="clickHandler">
			Show Custom Notification
		</button>
		<button class="showButton" @click="successHandler">
			Show Success Notification
		</button>		
		<button class="showButton" @click="errorHandler">
			Show Error Notification
		</button>		
		<button class="showButton" @click="warningHandler">
			Show Warning Notification
		</button>
		<button class="showButton" @click="infoHandler">
			Show Info Notification
		</button>
	</div>
	<Teleport to="#notification">
		<NotificationsList :notifications="notifications"></NotificationsList>
	</Teleport>
</template>

<style lang="scss" scoped>
.showButton {
	border-radius: 8px;
	border: 1px solid transparent;
	padding: 0.6em 1.2em;
	font-size: 1em;
	font-weight: 500;
	font-family: inherit;
	background-color: #1a1a1a;
	color: #f0f0f0;
	margin: 5px;
	cursor: pointer;
	transition: border-color 0.25s;

	&:hover {
		border-color: #646cff;
	}
	&:focus,
	&:focus-visible {
		outline: 4px auto -webkit-focus-ring-color;
	}
}
</style>
