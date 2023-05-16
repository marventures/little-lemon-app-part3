# React Native App

This is a React Native App using SectionList Component and StyleSheet API.

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### Screenshot

![image](https://user-images.githubusercontent.com/108392678/201504104-3d99679c-7dec-4a85-a159-84b933b78727.png)


### Links

- Solution URL: [Code](https://github.com/marventures/little-lemon-app-part3)

## My process

### Built with
- [React Native](https://reactnative.dev/docs/environment-setup) - React Native using Expo Go
- [SectionList](https://reactnative.dev/docs/sectionlist) - For lazy rendering menu items
- [StyleSheet](https://reactnative.dev/docs/stylesheet) - For styles

### What I learned

- Create a React Native App using Expo
- Use View, Text, and SectionList Components
- Create a Header Component
- Create a Footer Component  
- Create MenuItems component to display list of menu items and use SectionList
- Update Styles of Components to match Scenario
- Extract All Styles to StyleSheet API 
- Render Components to the App Component

Here is a code snippet: 


```jsx
const menuItemsToDisplay = [
  {
    title: 'Appetizers',
    data: [
      { name: 'Hummus', price: '$5.00' },
      { name: 'Moutabal', price: '$5.00' },
      { name: 'Falafel', price: '$7.50' },
      { name: 'Marinated Olives', price: '$5.00' },
      { name: 'Kofta', price: '$5.00' },
      { name: 'Eggplant Salad', price: '$8.50' },
    ],
  },
  ...
];

const Item = ({ name, price }) => (
  <View style={menuStyles.innerContainer}>
    <Text style={menuStyles.itemText}>{name}</Text>
    <Text style={menuStyles.itemText}>{price}</Text>
  </View>
);

const MenuItems = () => {
  const renderItem = ({ item }) => <Item name={item.name} price={item.price} />;

  const renderSectionHeader = ({ section: { title } }) => (
    <View style={menuStyles.headerStyle}>
      <Text style={menuStyles.sectionHeader}>{title}</Text>
    </View>
  );

  return (
    <View style={menuStyles.container}>
      <SectionList
        sections={menuItemsToDisplay}
        keyExtractor={(item, index) => item + index}
        renderItem={renderItem}
        renderSectionHeader={renderSectionHeader}
      />
    </View>
  );
};

const menuStyles = StyleSheet.create({
  container: {
    flex: 1,
  },
  ...
});

export default MenuItems;
```

### Useful resources

- [React Native Docs (StyleSheet) ](https://reactnative.dev/docs/stylesheet) - This helped me for all the neccessary React Native styles. I really liked their documentation and will use it going forward.  
- [React Native Docs (SectionList) ](https://reactnative.dev/docs/sectionlist) - This helped me for lazy rendering the MenuItem Components with Sections. 

## Author

- Website - [Marvin Morales Pacis](https://marvin-morales-pacis.vercel.app/)
- LinkedIn - [@marventures](https://www.linkedin.com/in/marventures/)
- Twitter - [@marventures11](https://www.twitter.com/marventures)
