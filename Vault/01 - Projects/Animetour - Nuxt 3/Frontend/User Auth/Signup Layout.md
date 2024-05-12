---
status: 🟨
tags:
  - project
area: "[[]]"
start: 
deadline: 
cssclasses:
  - center-titles
---
# Signup Navbar Layout Setup
---
==Navbar Layout Component(components/layout/Signup.vue)
```vue
<nav
class="fixed top-0 left-0 right-0 py-6 max-w-7xl mx-auto bg-gradient-to-r from-indigo-100"
>
	<div class="flex items-center flex-row-reverse space-x-4 space-x-reverse">
		<div>
		<Button variant="outline" size="lg" shape="round">Login</Button>
		</div>
		
		<div>
		<p class="text-xl text-muted-foreground">Already have an account</p>
		</div>
	</div>
</nav>

```
==Navbar Layout Component(layouts/login.vue)
```vue
<template lang="">
<LayoutSignup/>
<slot/> <!--Slot to hold the main component-->
</template>

```

## Signup Page Style
---
==Working on background and overlays can be handled easily as follows
- The signup_background class, has two elements
	- The background-image is to set the background image as well as to set a linear gradient.
	- The background-blend-mode class sets the gradient to be blended as an overlay
```vue
<div class="signup_background">
<!--Contents-->
</div>

<style scoped>
.signup_background {
background-image: url("/assets/pages/signup/background/signup_bg.jpg"),
linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.5));
background-blend-mode: overlay;
}
</style>
```


# Responsiveness
---
==Making the signup layout responsive:
- On the *first main-nav section* I want the nav to have a smaller padding on smaller displays and I set the original padding to be 2(when the display is <640px), and when the screen hits the ‘sm’(>640px) it will be 6 and on ‘lg’(>1024px) it will be 8.

- *On the second section* the Account Exist Section, I wanted the ‘Already have an account?’ prompt to be hidden on the small view and only the ‘Login‘ button to show up, to do this I used the ‘sm’(>640px) directive to make the content to be visible on displays starting from sm, and hidden on displays <640px.
```vue
<div class="relative">
//First Section
	<nav
	class="fixed mx-auto top-0 left-0 right-0 py-6 max-w-7xl px-2 sm:px-6 lg:px-8"
>	
		<div class="flex items-center flex-row-reverse space-x-4 space-x-reverse">
		
		<div>
		<Button variant="outline" size="lg" shape="round">Login</Button>
		</div>
	
		//Second Section
		<div class="hidden sm:block">
		<p class="text-xl text-white">Already have an account?</p>
		</div>
		
		</div>
	
	</nav>

</div>
```




# Related Resources
---
```dataview
list
from [[]] and #Resource 
```
