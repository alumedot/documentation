<template>
	<router-link :to="link" class="install-link">
		<span class="icon">
			<slot name="icon" />
		</span>
		<span class="text">
			<p class="title"><slot name="title" /></p>
			<p class="description"><slot name="description" /></p>
		</span>
    <span class="arrow">
     <!-- <IconSVG /> -->
     <img :src="$withBase('/assets/NextIcon.svg')" alt="foo">
    </span>

	</router-link>
</template>

<script>
	// import IconSVG from '../icons/NextIcon.svg';

	export default {
		name: 'InstallLink',
		props: {
			link: {
				type: String,
				required: true
			}
		},
		// components: {IconSVG}
	}
</script>

<style lang="scss" scoped>
// TODO: overrides branding.styl
.install-link {
	display: flex;
	align-items: center;
	// color: white;
	// padding: 16px;
	border-radius: 6px;
	margin: 16px 0; // You'd normally do layout margins etc from the parent, but seeing the parent
					// is a markdown file, that's a bit annoying

  &:hover {
    text-decoration: none !important;
  }

	.icon {
		flex-shrink: 0;
		width: 32px;
		margin-right: 16px;
		& ::v-deep svg {
			width: 100%;
			height: auto;
		}
	}
	.title {
		font-weight: 700;
		margin: 0;
	}
	.description {
		font-size: 12px;
		margin: 0;
	}
}
</style>

<!-- Copyrigth Directus - https://github.com/directus/docs/blob/master/.vuepress/theme/global-components/InstallLink.vue -->
