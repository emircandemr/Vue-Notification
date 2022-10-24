<script setup>
import { ref } from "vue";
import Notification from "./Notification.vue";

const props = defineProps(["notifications"]);
const removeId = ref(null);

const clickHandler = () => {
	props.notifications.forEach((element) => {
		if (element.id === parseInt(removeId.value)) {
			element.show = false;
		}});
};
</script>

<template>
	<div class="notifications" :class="props.notifications[0]?.class.position">
		<template v-for="notification in props.notifications" :key="notification.id">
			<Notification
			v-if="notification.show" 
			v-model:id="removeId"
			:notification="notification"
			@click="clickHandler">
			</Notification>
		</template>
	</div>
</template>

<style scoped lang="scss">
.notifications {
	position: fixed;
	margin: 8px;
}
</style>
