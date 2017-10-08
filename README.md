# typescript-sort-completions

## Notice
You must install plugin manually via npm/yarn (see below) otherwise the TS service won't load it

## Installation

```npm install typescript-type-completion-sorting-plugin --save-dev```

Add to your tsconfig.json:

```json
    "plugins": [{
         "name": "typescript-type-completion-sorting-plugin"
    }]
```

## Features

When doing completion from TS service, slightly reorder available completions to keep own non-inherited properties from type at the top of completion list:

## React (especially useful when inherting from HTMLAttributes)

### Before: 
![react before](/images/react-before.png) 

(Component own properties are messed with HTML ones)

### After: 
![react after](/images/react-after.png)

(Notice component own properites are being displayed at top)

## Class

### Before

![class1 before](/images/class1-before.png)

(Mix own & inherited properties)

### After:

![class1 after](/images/class1-after.png)

(Own properties are being displayed at top)

### Before:

![class2 before](/images/class2-before.png)

### After:

![class2 after](/images/class2-after.png)

(Own properties are being displayed at top)


## Known issues

Non working with JSX elements without closing tag, i.e:
```tsx
return <MyComp /*trigger completion here*/
```
Completions won't be broken, but will be reverted to usual, non-filtered completions

*Workaround*

Enclose expression in brackets:
```tsx
return (<MyComp /*trigger here*/);
```

## Release Notes

### 0.0.1-0.0.3

Initial release 
