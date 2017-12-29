# React Burger Builder

This project is from the [React Udemy Course](https://www.udemy.com/react-the-complete-guide-incl-redux/) I am following as part of my month of learning React project I started on December 1st.  Information about that project can be found at [at this repo](https://github.com/xmtrinidad/UdemyReact)

## About

Section 8 of the Udemy React course creates a burger builder that uses concepts from sections 1-7, which includes:
* Functional Components
* Class Components with state
* Utilizing various ES6 concepts to create dynamic components
* Project structure and best practices

I've done a few of my own projects using the concepts from these sections whle also following along with the tutorial for the Burger Builder.  Checkout my [github repos](https://github.com/xmtrinidad) to view them.

I will update this readme with notable things I've learned from following along through the development of this application.

---

**Update 12/29**        

I've finally finished the Burger Builder section from the Udemy course and these are the things that stood at the most to me:

### Everything can be broken down into components

There were several situations where I didn't think it would be necessary to create components, but as I followed along with the tutorial it made sense why even small elements could be broken down into components.

One notable example was breaking down a list into sub-components.  Below is what the *navigationItems* component looks like:
```jsx
const navigationItems = () => (
    <ul className={classes.NavigationItems}>
        <NavigationItem link="/" active>Burger Builder</NavigationItem>
        <NavigationItem link="/">Checkout</NavigationItem>
    </ul>
);
```

Within the *navigationItems* is the *navigationItem* component, which are the ```<li> ``` elements of the list:

```jsx
const navigationItem = (props) => (
    <li className={classes.NavigationItem}>
        <a 
            className={props.active ? classes.active : null}
            href={props.link}>{props.children}</a>
    </li>
);
```

Although the ```<li>``` elements didn't need to be separated into their own components, they have a fair amount of CSS associated with them.  By breaking the <li> elements into their own components, the CSS becomes much easier to maintain.

### Folder Structure

Throughout the section, the tutorial covers best practices as far as folder structure.  The app remains consistent with separating components and containers, and creating subcomponents within components that are logically grouped together, but at the same time separating components that will be used in other areas.

For example, there is a *UI* folder that contain a backdrop, button, and modal components.  These components are linked with any single component because they are used in multiple places, which is why they're in their own folder.

Other components like the Navigation have their own folder and within that folder are other components that are attached to the Navigation.