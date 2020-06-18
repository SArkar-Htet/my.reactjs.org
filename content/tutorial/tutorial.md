---
id: tutorial
title: "Tutorial: React မိတ်ဆက်"
layout: tutorial
sectionid: tutorial
permalink: tutorial/tutorial.html
redirect_from:
  - "docs/tutorial.html"
  - "docs/why-react.html"
  - "docs/tutorial-ja-JP.html"
  - "docs/tutorial-ko-KR.html"
  - "docs/tutorial-zh-CN.html"
---

ဤသင်ခန်းစာသည် Reactနှင့်ပတ်သတ်၍ သိရှိခဲ့ပြီးသော အသိပညာဗဟုသုတများနှင့် မသက်ဆိုင်ပါ။

## သင်ခန်းစာကို ငါတို့မစတင်မီ {#before-we-start-the-tutorial}

ဤသင်ခန်းစာမှာ အသေးစားဂိမ်းလေးတစ်ခုဆောက်ပါမည်။ **သင်က ဂိမ်းတွေကို တည်ဆောက်သူမဟုတ်တဲ့အတွက်ကြောင့် ဒါကို ကျော်သွားနိုင်ပါသည်။ ဒါပေမယ့် ကြိုးစားကြည့်ပါ။** သင်ခန်းစာမှာ လေ့လာရမည့်နည်းစနစ်များသည်မည်သည့် React app ကို မဆိုတည်ဆောက်ရန် အခြေခံဖြစ်တာကြောင့် ဒါကိုကျွမ်းကျင်ရင် ကောင်းကောင်းနားလည်သွားမည်ဖြစ်ပါသည်။

>အကြံပြုချက်
>
>ဤသင်ခန်းစာသည် လေ့လာရင်း တစ်ပါတည်း လုပ်ဆောင်တက်သူများ အတွက် ရည်ရွယ်ပါသည်။ အကယ်၍ သဘောတရားများကို အခြေခံမှစ၍ သင်ယူခြင်းကို ပိုနှစ်သက်ပါက ကျွန်ုပ်တို့၏ [step-by-step guide](/docs/hello-world.html)ကို သွားရောက်ကြည့်ရှုပါ။ သင်ခန်းစာနှင့် လမ်းညွှန်ချက်သည် တစ်ခုနဲ့တစ်ခု ဆ​က်စပ်နေတာကို တွေ့နိုင်ပါသည်။

သင်ခန်းစာကို အောက်ပါအတိုင်းကဏ္ဍများခွဲထားပါသည်:

* [Setup for the Tutorial](#setup-for-the-tutorial) သည် သင်ခန်းစာမှာ လိုက်ပါလုပ်ဆောင်ရမည့် **လမ်းစတစ်ခုကို** ပေးပါလိမ့်မည်။
* [Overview](#overview) သည် React၏ **အခြေခံတွေဖြစ်သည့်** components၊ props၊ နှင့် state တို့ကို သင်ပေးပါလိမ့်မည်။
* [Completing the Game](#completing-the-game) သည် React developmentတွင် **အသုံးများဆုံးဖြစ်သည့် နည်းစနစ်များကို** သင်ပေးပါလိမ့်မည်။
* [Adding Time Travel](#adding-time-travel) သည် React၏ ထူးခြားသော အားသာချက်များကို **နက်နက်ရှိုင်းရှိုင်းနားလည်** စေပါလိမ့်မည်။

ဤသင်ခန်းစာကို ကျွမ်းကျင်ဖို့ တစ်ကြိမ်တည်းဖြင့် အပိုင်းအားလုံးကို အပြီးလေ့လာရန် မလိုပါ။ တစ်ပိုင်း (သို့မဟုတ်) နှစ်ပိုင်း ဖြစ်ဖြစ် သင်တတ်နိုင်သလောက် ကြိုးစားပါ။

### ငါတို့ ဘာကို တည်ဆောက်ကြမှာလဲ? {#what-are-we-building}

သင်ခန်းစာထဲမှာ interactiveဖြစ်သည့် tic-tac-toe game တစ်ခုကို Reactဖြင့် ဘယ်လိုတည်ဆောက်ရမလဲဆိုတာ ပြပေးပါမည်။

ကျွန်ုပ်တို့ ဘာကိုတည်ဆောက်မလဲဆိုတာ **[Final Result](https://codepen.io/gaearon/pen/gWWZgR?editors=0010)** မှာ သင်မြင်နိုင်ပါသည်။ အကယ်၍ codeကို နားမလည်လျှင် (သို့မဟုတ်) codeရဲ့ ရေးသားနည်းကို အကျွမ်းတဝင်မရှိလျှင် စိတ်ပူရန်မလိုပါ။ ဒီသင်ခန်းစာရဲ့ ရည်ရွယ်ချက်က သင့်ကို React နှင့် ၄င်း၏ ရေးသားနည်းကို နားလည်ရန်ကူညီဖို့ ဖြစ်ပါသည်။

သင်ခန်းစာကိုမဆက်မီ tic-tac-toe game ကို ကြည့်ရှုရန် အကြံပြုလိုပါသည်။ သတိထားမိလိမ့်မည့် အချက်တစ်ချက်ကတော့ game board၏ ညာဘက်က အမှတ်စဥ်စာရင်းဖြစ်ပါသည်။ ဒီစာရင်းသည် သင်gameထဲမှာလုပ်ခဲ့သည့် ရွှေ့လျားမှုတွေအားလုံး၏ မှတ်တမ်းတစ်ခုကိုပေးပြီး ၄င်းသည် game၏ လှုပ်ရှားမှုအလိုက် ပြုပြင်ပေးပါသည်။

tic-tac-toe game ကို အကျွမ်းတဝင်ရှိလျှင် ပိတ်နိုင်ပါသည်။ ဤသင်ခန်းစာတွင်ရိုးရှင်းသော template မှစတင်ပါမည်။ နောက်တစ်ဆင့်သည် game ကိုစတင်တည်ဆောက်နိုင်စေရန် ပြင်ဆင်ပေးရန်ဖြစ်ပါသည်။

### လိုအပ်ချက်များ {#prerequisites}

သင်အနေဖြင့် HTML, Javascript တို့ကို ရင်းနှီးလိမ့်မည်လို့ ယူဆပါတယ်။ သို့သော် အခြား programming language တစ်ခုမှလာခဲ့လျှင်ပင် လိုက်လုပ်နိုင်သင့်ပါသည်။ သင့်ကို programming ၏ သဘောတရားများဖြစ်သော functions, objects, arrays, classes နှင့် lesser extent တို့ဖြင့် ရင်းနှီးကျွမ်းဝင်လိမ့်မည်လို့ မှတ်ယူပါသည်။

အကယ်၍ JavaScript ကိုပြန်လည်လေ့လာရန် လိုအပ်ပါက [this guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)ကို ဖတ်ရန် အကြံပြုပါသည်။ React သည် JavaScript ၏ လက်ရှိ version တစ်ခုဖြစ်သော ES6မှ အချို့သော features များကို အသုံးပြုနေကြောင်း သတိပြုပါ။ ဤသင်ခန်းစာတွင် arrow functions, classes, let နှင့် const စသည့် statements များကို အသုံးပြုပါသည်။ ES6 code ကို ဘယ်လို compileလုပ်လဲဆိုသည်ကို လေ့လာရန် [Babel REPL](babel://es5-syntax-example) တွင် လေ့လာနိုင်သည်။

## သင်ခန်းစာအတွက် ပြင်ဆင်ခြင်း {#setup-for-the-tutorial}

ဒီသင်ခန်းစာကို ပြီးမြောက်ရန် နည်းလမ်းနှစ်မျိုးရှိပါသည်။ browser တွင် code ကို ရေးသောနည်း သို့မဟုတ် သင်၏ compute ထဲတွင် Local Development Environment တစ်ခုတည်ဆောက်သော နည်းတို့ဖြစ်သည်။

### ပြင်ဆင်ခြင်း နည်းလမ်း ၁: Browser တွင် Code ရေးခြင်း {#setup-option-1-write-code-in-the-browser}

ဒီနည်းလမ်းသည် စတင်ဆောင်ရွက်ရန် အမြန်ဆုံးဖြစ်ပါသည်။

ပထမဦးစွာ browser တွင် **[Starter Code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)** ကို tabအသစ်ဖြင့် ဖွင့်ပါ။ tab အသစ်တွင် tic-tac-toe Game Board အလွတ်တစ်ခုနှင့် React codeကို ပြပါလိမ့်မည်။ ဒီသင်ခန်းစာတွင် ကျွန်ုပ်တို့သည် React codeကို ပြင်ဆင်ပါမည်။

ယခု သင်သည် ဒုတိယနည်းလမ်းကို ကျော်သွားနိုင်ပြီး React ၏ အခြခံအကျဥ်းချုပ်ကို လေ့လာရန် [Overview](#overview) အခန်းကဏ္ဍကို သွားနိုင်ပါသည်။

### ပြင်ဆင်ခြင်း နည်းလမ်း ၂: Local Development Environment {#setup-option-2-local-development-environment}

ဤနည်းလမ်းသည် ယခုသင်ခန်းစာအတွက် မဖြစ်မနေမလိုအပ်ပါ။

<br>

<details>

<summary><b>Optional: သင့်စက်ထဲတွင် လမ်းညွှန်ချက်တွေကို လိုက်ပါလုပ်ဆောင်ဖို့အတွက် သင်ကြိုက်တဲ့ text editorကို အသုံးပြုနိုင်ပါသည်။</b></summary>

ဤနည်းလမ်းသည် အလုပ်များသော်လည်း သင်ရွေးချယ်ထားသော text editor ကို သုံး၍ သင်ခန်းစာကို ပြီးမြောက်ရန် လုပ်ဆောင်နိုင်ပါသည်။ လုပ်ဆောင်ရမည့် အဆင့်များမှာ- 

၁။ [Node.js](https://nodejs.org/en/) ၏ လက်ရှိ version ကို ထည့်သွင်းပါ။  
၂။ Project အသစ်တစ်ခုပြုလုပ်ရန် [installation instructions for Create React App](/docs/create-a-new-react-app.html#create-react-app) မှ ညွှန်ကြားချက်များကို လိုက်နာပါ။

```bash
npx create-react-app my-app
```

၃. project ၏ `src/` folder ထဲမှ ဖိုင်အားလုံးကို ဖျက်ပါ။

> သတိပြုရန်:
>
>**ရှိပြီးသား `src` folder ကို ဖျက်ရန်မလိုပါ။ ၄င်းထဲတွင်ရှိသော မူရင်းဖိုင်များကိုသာ ဆိုလိုခြင်းဖြစ်ပါသည်။** နောက်တစ်ဆင့်တွင် ဥပမာများနှင့်အတူ မူရင်းဖိုင်များကို ပြန်လည်အစားထိုးပါမည်။

```bash
cd my-app
cd src

# If you're using a Mac or Linux:
rm -f *

# Or, if you're on Windows:
del *

# Then, switch back to the project folder
cd ..
```

4. [this CSS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0100) ဖြင့် `src/` folder ထဲတွင် `index.css` အမည်ဖြင့် ဖိုင်တစ်ခုထည့်သွင်းပါ။

5. [this JS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010) ဖြင့် `src/` folder ထဲတွင် `index.js` အမည်ဖြင့် ဖိုင်တစ်ခုထည့်သွင်းပါ။

6. `src/` folder ထဲမှ `index.js` ဖိုင်၏ အပေါ်ဘက်တွင် အောက်ပါသုံးကြောင်းကို ထည့်ပါ။

```js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
```

ယခု project folder ထဲတွင် `npm start` ဆိုသော command ကို run ပြီး browser ထဲတွင် `http://localhost:3000` ကို ဖွင့်လိုက်လျှင် tic-tac-toe အကွက်လွတ်တစ်ခုကို သင်မြင်ရပါလိမ့်မည်။

သင့်၏ editor အတွက် syntax highlighting ကို configure လုပ်ရန် ဤညွှန်ကြားချက် [these instructions](https://babeljs.io/docs/editors/) ကို လိုက်နာဖို့ အကြံပြုပါသည်။

</details>

### ကူညီပါ, ငါအခက်ခဲကြုံနေပြီ! {#help-im-stuck}

သင်အခက်ခဲကြုံနေလျှင် [community support resources](/community/support.html) ကို ကြည့်ရှုလေ့လာ  ပါ။ အထူးသဖြင့် [Reactiflux Chat](https://discord.gg/reactiflux) သည် အကူညီကို လျှင်မြန်စွာရယူရန် နည်းလမ်းကောင်းတစ်ခုဖြစ်ပါသည်။ သင်သည်အဖြေကို မရရှိလျှင် (သို့မဟုတ်) အခက်ခဲကြုံနေသေးလျှင် ကျေးဇူးပြု၍ ပြသနာကိုတင်ပြပြီး ငါတို့အကူညီကို ရယူပါ။

## အနှစ်ချုပ် {#overview}

set up လုပ်ပြီးပါက React ၏ အနှစ်ချုပ်ကို ကြည့်ကြရအောင်။

### React ဆိုတာဘာလဲ? {#what-is-react}

React သည် user interfaces တည်ဆောက်ရန်အတွက် ပြောင်းလွယ်ပြင်လွယ်ပြီး ထိရောက်သော၊ declarative ရေးသားနည်းပုံစံ အသုံးပြုထားသော Javascript library ဖြစ်သည်။ ၄င်းသည် "components" ဟု ခေါ်သော သေးငယ်ပြီး သီးသန့်ရှိသော code အစိတ်အပိုင်းလေးများမှ ရှုပ်ထွေးသော UI များကို ရေးသားနိုင်သည်။

Reactတွင် အနည်းငယ်မတူညီသော components များ ရှိကြသော်လည်း `React.Component` subclasses များနှင့် စတင်ပါမည်-

```javascript
class ShoppingList extends React.Component {
  render() {
    return (
      <div className="shopping-list">
        <h1>Shopping List for {this.props.name}</h1>
        <ul>
          <li>Instagram</li>
          <li>WhatsApp</li>
          <li>Oculus</li>
        </ul>
      </div>
    );
  }
}

// Example usage: <ShoppingList name="Mark" />
```

မကြာမီတွင် ငါတို့သည် XML-like tag များကို ရရှိပါလိမ့်မည်။ Screen ပေါ်တွင် ကျွန်ုပ်တို့အလိုရှိရာကို Reactအား ခိုင်းစေရန် component များကို အသုံးပြုပါသည်။ component ၏ အချက်အလက်အချို့ပြောင်းလဲသွားသောအခါ Reactသည် ကျွန်ုပ်တို့၏ component များကို လိုအပ်ချက်အလိုက် ပြုပြင်မွမ်းမံခြင်းနှင့် re-render ကို လုပ်ပါလိမ့်မည်။

အထက်ပါပုံကို ကြည့်ပါ။ ShoppingList သည် **React component class** (သို့မဟုတ်) **React component type** တစ်ခုဖြစ်ပါသည်။ component တစ်ခုသည် `props` ("properties" ၏ အတိုကောက်) ကို parameter ထဲတွင် ယူပြီး `render` method မှ တစ်ဆင့် ပြသရန် viewsများကို အဆင့်ဆင့်ပြန်ပေးသည်။

`render` method သည် screen ပေါ်တွင်သင်မြင်တွေ့လိုသော *ဖော်ပြချက်တစ်ခုကို* ပြန်ပေးပါသည်။ React သည် ဖော်ပြချက်ကို ရယူပြီး ရလဒ်ကို ပြသပါသည်။ အထူးသဖြင့် `render` မှ ပြန်ပေးလိုက်သော **React element** တစ်ခုသည် ဘာကို render လုပ်မလဲ ဆိုတာ၏ ပေါ့ပါးသော ဖော်ပြချက်တစ်ခုဖြစ်ပါသည်။ React Developers အများစုသည် "JSX" ဟုခေါ်သော ဤနည်းစနစ်များကို ရေးသားရန်ပိုမိုလွယ်ကူသည့် Special Syntax တစ်ခုကို အသုံးပြုပါသည်။ `<div />` syntax သည် တည်ဆောက်ချိန်တွင် `React.createElement('div')` သို့ ပြောင်းလဲပါသည်။ အထက်တွင် ဖော်ပြခဲ့သော ဥပမာနှင့် တူပါသည်-

```javascript
return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', /* ... h1 children ... */),
  React.createElement('ul', /* ... ul children ... */)
);
```

[အကျယ်ကို ဤတွင် ကြည့်ပါ။](babel://tutorial-expanded-version)

သင်သိလိုလျှင် `createElement()` ကို [API reference](/docs/react-api.html#createelement) ထဲတွင် အသေးစိတ်ဖော်ပြထားပါသည်။ သို့သော်လည်း ၄င်းကို သင်ခန်းစာထဲတွင် အသုံးပြုမည်မဟုတ်ပါ။ ၄င်းအစား JSX ကို ဆက်လက်အသုံးပြုသွားပါမည်။

JSXသည် JavaScript ၏ စွမ်းအားအပြည့်ပါရှိပါသည်။ ထို့ကြောင့် *မည်သည့်* JavaScript အသုံးနှုန်းကိုမဆို JSX ထဲရှိ ကွင်းထဲတွင် ထည့်ထားနိုင်သည်။ React element တစ်ခုချင်းစီသည် JavaScript ၏ object တစ်ခုဖြစ်ပြီး ၄င်းတို့ကို variable တစ်ခုထဲတွင် သိမ်းနိုင်သည် (သို့မဟုတ်) program တစ်လျှောက် လှည့်ပတ်အသုံးပြုနိုင်သည်။

အထက်တွင် ပါရှိသော `ShoppingList` component သည် `<div />` နှင့် `<li />` ကဲသို့သော built-in DOM Components များကိုသာ render လုပ်ပါသည်။ သို့သော် ကြိုက်နှစ်သက်ရာ React Component များကိုလည်း compose, render လုပ်နိုင်ပါသည်။ ဥပမာ `<ShoppingList />` ဟု ရေးသားလိုက်ခြင်းဖြင့် `ShoppingList` component တစ်ခုလုံးကို ရည်ညွှန်းနိုင်ပါသည်။ React Component တစ်ခုချင်းသည် အတိုဆုံးနှင့်အရှင်းဆုံးဖော်ပြပြီး လွတ်လပ်စွာ လှည့်ပတ်နိုင်ပါသည်။ ၄င်းသည် ရိုးရှင်းသော component များမှ ရှုပ်ထွေးသော UI များကို တည်ဆောက်နိုင်ပါသည်။ 

## Starter Code ကို စစ်ဆေးခြင်း {#inspecting-the-starter-code}

သင်ခန်းစာကို **Browser** တွင် လုပ်လိုလျှင် new tab တစ်ခုတွင် ဤ **[Starter Code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)** ကို ဖွင့်ပါ။ သင်ခန်းစာကို **သင့်စက်ထဲတွင်** လုပ်လိုလျှင် သင့် Project Folder ထဲမှ `src/index.js` ကို ဖွင့်ပါ ([setup](#setup-option-2-local-development-environment) လုပ်စဉ်အတောတွင်း ဤဖိုင်ကို သင်ထိတွေ့ခဲ့ပြီးပါပြီ)။ 

ဤ Starter Code သည် ကျွန်ုပ်တို့ တည်ဆောက်နေသောအရာ၏ အခြေခံဖြစ်ပါသည်။ ကျွန်ုပ်တို့သည် CSS ကို ထောက်ပံ့ပေးပါသည်။ ထို့ကြောင့် သင်အနေနှင့် React လေ့လာချင်းအပေါ် နှင့် tic-tac-toe game ကို ရေးဆွဲရာတွင်သာ အာရုံစိုက်ရန် လိုပါသည်။

Code ကို စစ်ဆေးခြင်းအားဖြင့် React Components သုံးခုရှိသည်ကို သင်သတိပြုမိလိမ့်မည်။ 

* Square
* Board
* Game

Square Component သည် `<button>` တစ်ခုတည်းကို render လုပ်ပြီး Board သည် စတုရန်းကွက် ၉ ကွက်ကို render လုပ်သည်။ Game Component သည် နေရာချမည့် တန်ဖိုးများပါဝင်သည့် board တစ်ခုကို render လုပ်ပါသည်။ ၄င်းကိုတော့ နောက်မှ ပြန်လည်ပြုပြင်ပါမည်။ ယခုအချိန်တွင် componentများသည် interactive မဖြစ်သေးပါ။

### Prop များမှ တစ်ဆင့် ဒေတာပေးပို့ခြင်း {#passing-data-through-props}

Board Component မှ Square Component ဆီသို့ ဒေတာအချို့ကို ကူးပြောင်းကြည့်ကြပါစို့။

သင်ခန်းစာကို လက်တွေ့လုပ်ဆောင်နေချိန်မှာ code တွေကို ကူးချခြင်းမပြုဘဲ လက်နဲ့ရေးရန် အထူးအကြံပြုပါသည်။ ဤအရာသည် သင်၏ မှတ်ညာဏ်ကို ပိုမိုကောင်းလာစေရန် နှင့် ပိုမိုနားလည်သဘောပေါက်စေရန် ကူညီပါလိမ့်မည်။

Board Component ၏ `renderSquare` method အတွင်းတွင် Square Component သို့ `value` ဟုခေါ်သော prop တစ်ခုကို ပေးပို့ရန် code ကို ပြင်ဆင်ပါ။

```js{3}
class Board extends React.Component {
  renderSquare(i) {
    return <Square value={i} />;
  }
}
```
`{/* TODO */}` ကို `{this.props.value}` နှင့် အစားထိုးခြင်းဖြင့် ၄င်း၏ တန်ဖိုးကို ပြသရန် Square Component ၏ `render` Method ကို ပြင်ဆင်ပါ။

```js{5}
class Square extends React.Component {
  render() {
    return (
      <button className="square">
        {this.props.value}
      </button>
    );
  }
}
```

မပြင်ဆင်မီ:

![React Devtools](../images/tutorial/tictac-empty.png)

ပြင်ဆင်ပြီး: စတုရန်းကွက်တိုင်း၏ အတွင်းတွင် နံပါတ်တစ်ခုကို မြင်တွေ့နိုင်ပါသည်။

![React Devtools](../images/tutorial/tictac-numbers.png)

**[ဤနေရာတွင် Code အပြည့်စုံကို ကြည့်ပါ](https://codepen.io/gaearon/pen/aWWQOG?editors=0010)**

ဂုဏ်ယူပါတယ်! Board Component မှ Square Component ဆီသို့ "prop တစ်ခုကို သင်ပေးပို့"လိုက်ပါပြီ။ React app များတွင် props ပေးပို့ခြင်းသည် Parent Component များမှ Child Component ဆီသို့ အချက်အလက်များစီးဆင်းပုံဖြစ်သည်။

### Interactive Component တစ်ခုပြုလုပ်ခြင်း {#making-an-interactive-component}

Square Component ကို နှိပ်လိုက်ချိန်တွင် "X" နှင့် ဖြည့်စွက်အစားထိုးပါ။ ပထမဦးစွာ Square Component ၏ `render()` Function မှ ပြန်လာသော button tag ကို ပြောင်းလဲပြင်ဆင်ပါ။

```javascript{4}
class Square extends React.Component {
  render() {
    return (
      <button className="square" onClick={function() { alert('click'); }}>
        {this.props.value}
      </button>
    );
  }
}
```

စတုရန်းတစ်ကွက်ပေါ်သို့ နှိပ်လိုက်လျှင် Browser ၌ alert box တစ်ခုကို မြင်နိုင်ပါသည်။

>မှတ်ချက်
>
>စာရိုက်ခြင်းကို သက်သာစေရန်နှင့် [`၄င်း၏` ရှုပ်ထွေးမှုများ](https://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/) မဖြစ်စေရန် အောက်တွင်ဖော်ပြထားသော [arrow function ရေးထုံးကို](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) Event Handler များအတွက် အသုံးပြုပါမည်။ 
>
>```javascript{4}
>class Square extends React.Component {
>  render() {
>    return (
>      <button className="square" onClick={() => alert('click')}>
>        {this.props.value}
>      </button>
>    );
>  }
>}
>```
>
> `onClick={() => alert('click')}` နှင့်အတူ `onClick` prop ကဲသို့ *function တစ်ခုကို* ဘယ်လိုပေးပို့လဲဆိုတာ သတိပြုပါ။ `() =>` ကို မေ့ထားပြီး `onClick={alert('click')}` ဟု ရေးခြင်းသည် မှားနေကျ အမှားတစ်ခုဖြစ်ပြီး Component ကို re-render လုပ်သည့် အချိန်တိုင်းတွင် alert box ကို ဖော်ပြနေမည်။

နောက်တစ်ဆင့်အနေဖြင့် Square Component ကို နှိပ်လိုက်ကြောင်း "သိစေပြီး" ၄င်းကို "X" အမှတ်အသားဖြင့် ဖြည့်စွက်လိုသည်။ ထိုအရာများကို သိစေရန် Component များသည် **state** ကို သုံးပါသည်။

React Component များသည် သူတို့၏ Constructorများထဲတွင် `this.state` ကို ထည့်သွင်းကြော်ငြာခြင်းဖြင့် state ကို ရရှိနိုင်ပါသည်။ `this.state` ကို ၄င်းအားသတ်မှတ်ထားသော React Component တစ်ခုထဲမှာဘဲ private အဖြစ် ထည့်သွင်းစဥ်းစားသင့်သည်။ `this.state` ထဲတွင် Square Component ၏ လက်ရှိတန်ဖိုးကို သိမ်းဆည်းပြီး Square Component ကို နှိပ်လိုက်သောအခါ ၄င်းကို ပြောင်းလဲကြပါစို့။

ပထမဦးစွာ state ကို စတင်ရန် Class အတွင်းတွင် Constructor တစ်ခု ထည့်ပါမည်။

```javascript{2-7}
class Square extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: null,
    };
  }

  render() {
    return (
      <button className="square" onClick={() => alert('click')}>
        {this.props.value}
      </button>
    );
  }
}
```

>မှတ်ချက်
>
>[JavaScript classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) များတွင် Subclass တစ်ခု၏ Constructor သတ်မှတ်သောအခါ `super` ဟု အမြဲခေါ်ပေးရန် လိုအပ်ပါသည်။ `constructor` တစ်ခုရှိသော React Component Class များအားလုံးသည် `super(props)` တစ်ခုကို ခေါ်ခြင်းနှင့် စတင်သင့်ပါသည်။

click နှိပ်လိုက်ချိန်တွင် လက်ရှိ state ၏ တန်ဖိုးကို ဖော်ပြရန် Square ၏ `render` method ကို ပြောင်းလဲပါမည်။

* `<button>` tag အတွင်းတ္ငင်`this.state.value` နှင့် `this.props.value` ကို အစားထိုးပါ။
* `onClick={() => this.setState({value: 'X'})}` နှင့် `onClick={...}` ကို အစားထိုးပါ။
* ဖတ်ရပိုမိုလွယ်ကူစေရန် `className` နှင့် `onClick` prop များကို သီးခြားလိုင်းများပေါ်တွင် ထားပါ။

ထိုပြောင်းလဲမှုများပြီးသွားသောအခါ Square ၏ `render` method ဖြင့် ပြန်လာသော `<button>` tag ကို မြင်ရပါသည်။

```javascript{12-13,15}
class Square extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: null,
    };
  }

  render() {
    return (
      <button
        className="square"
        onClick={() => this.setState({value: 'X'})}
      >
        {this.state.value}
      </button>
    );
  }
}
```

Square ၏ `render` method အတွင်းတွင် `onClick` handler တစ်ခုမှ `this.setState` ကို ခေါ်ခြင်းအားဖြင့် `<button>` နှိပ်လိုက်တိုင်း ဤ Square ကို re-render လုပ်ရန် React ကို ပြောသည်။ ဤပြင်ဆင်မှုပြီးနောက် Square ၏ `this.state.value` သည် `'X'` ဖြစ်လာသည်။ ထို့ကြောင့် Game Board ပေါ်တွင် `X` ကို မြင်ရပါလိမ့်မည်။ မည်သည့် စတုရန်းကွက်ပေါ်မဆို နှိပ်လိုက်လျှင် `X` တစ်ခုပေါ်လာလိမ့်မည်။

Component တစ်ခုအတွင်းတွင် `setState` ကို ခေါ်လိုက်သောအခါ React သည် ၄င်းအတွင်းမှာရှိသည့် Child Component များကို ထိုနည်းတူ အလိုလျောက်ပြင်ဆင်ပါသည်။

**[ဤနေရာတွင် Code အပြည့်စုံကို ကြည့်ပါ](https://codepen.io/gaearon/pen/VbbVLg?editors=0010)**

### Developer Tools {#developer-tools}

[Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en) နှင့် [Firefox](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/) များအတွက် React Devtools extension သည် browser ၏ developer tools များနှင့်အတူ React component tree အားစစ်ဆေးခွင့်ပြုသည်။

<img src="../images/tutorial/devtools.png" alt="React Devtools" style="max-width: 100%">

React DevTool များသည် React Component များ၏ prop များနှင့် state ကို စစ်ဆေးခွင့်ပြုသည်။

React DevTool များ သွင်းပြီးနောက် Developer Tool များအား ဖွင့်ရန် Page ပေါ်မှ မည်သည့် element ပေါ်တွင်မဆို right-click နှိပ်ပြီး "Inspect" ကို နှိပ်ပါ။ React tab များဖြစ်သည့် ("⚛️ Components" and "⚛️ Profiler") တို့သည် ညာဘက်အစွန်ဆုံးတွင် ပေါ်လာလိမ့်မည်။ Component Tree ကို စစ်ဆေးရန် "⚛️ Components" ကို အသုံးပြုပါ။

**သို့သော်, ၄င်းကို CodePen နှင့် အလုပ်လုပ်ရန် အဆင့်အနည်းငယ်ရှိသည်ကို သတိပြုပါ၊**

1. Log in or register လုပ်ပြီး သင့် email ကို အတည်ပြုပါ (spam များကို ကာကွယ်ရန် လိုအပ်သည်)။
2. "Fork" button ကို နှိပ်ပါ။
3. "Change View" ကို နှိပ်ပြီးနောက် "Debug mode" ကို ရွေးပါ။
4. ပွင့်လာသော new tab အတွင်းတွင်, Devtool များသည် React tab တစ်ခုရှိသင့်သည်။

## Game ပြီးဆုံးခြင်း {#completing-the-game}

ယခုတွင် ကျွန်ုပ်တို့၏ tic-tac-toe game အတွက် အခြခံအုတ်မြစ်များရှိနေပါပြီ။ ပြီးပြည့်စုံသော game တစ်ခုရရှိရန် "X" များနှင့် "O" များကို game board ပေါ်တွင် အစားထိုးနေရာချရန် လိုအပ်ပြီး အနိုင်ရရှိသူကို သတ်မှတ်ရန် နည်းလမ်းတစ်ခုလိုအပ်ပါသည်။

### Lifting State Up {#lifting-state-up}

လက်ရှိတွင် Square Component တစ်ခုစီသည် Game ၏ state ကို ထိန်းသိမ်းထားသည်။ အနိုင်ရရှိသူကို ကြေငြာရန် တစ်နေရာတည်းတွင် စတုရန်း ၉ ကွက်လုံး၏ တန်ဖိုးတစ်ခုချင်းစီကို ထိန်းသိမ်းရလိမ့်မည်။

We may think that Board should just ask each Square for the Square's state. Although this approach is possible in React, we discourage it because the code becomes difficult to understand, susceptible to bugs, and hard to refactor. Instead, the best approach is to store the game's state in the parent Board component instead of in each Square. The Board component can tell each Square what to display by passing a prop, [just like we did when we passed a number to each Square](#passing-data-through-props).

**To collect data from multiple children, or to have two child components communicate with each other, you need to declare the shared state in their parent component instead. The parent component can pass the state back down to the children by using props; this keeps the child components in sync with each other and with the parent component.**

Lifting state into a parent component is common when React components are refactored -- let's take this opportunity to try it out.

Add a constructor to the Board and set the Board's initial state to contain an array of 9 nulls corresponding to the 9 squares:

```javascript{2-7}
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
    };
  }

  renderSquare(i) {
    return <Square value={i} />;
  }
```

When we fill the board in later, the `this.state.squares` array will look something like this:

```javascript
[
  'O', null, 'X',
  'X', 'X', 'O',
  'O', null, null,
]
```

The Board's `renderSquare` method currently looks like this:

```javascript
  renderSquare(i) {
    return <Square value={i} />;
  }
```

In the beginning, we [passed the `value` prop down](#passing-data-through-props) from the Board to show numbers from 0 to 8 in every Square. In a different previous step, we replaced the numbers with an "X" mark [determined by Square's own state](#making-an-interactive-component). This is why Square currently ignores the `value` prop passed to it by the Board.

We will now use the prop passing mechanism again. We will modify the Board to instruct each individual Square about its current value (`'X'`, `'O'`, or `null`). We have already defined the `squares` array in the Board's constructor, and we will modify the Board's `renderSquare` method to read from it:

```javascript{2}
  renderSquare(i) {
    return <Square value={this.state.squares[i]} />;
  }
```

**[View the full code at this point](https://codepen.io/gaearon/pen/gWWQPY?editors=0010)**

Each Square will now receive a `value` prop that will either be `'X'`, `'O'`, or `null` for empty squares.

Next, we need to change what happens when a Square is clicked. The Board component now maintains which squares are filled. We need to create a way for the Square to update the Board's state. Since state is considered to be private to a component that defines it, we cannot update the Board's state directly from Square.

Instead, we'll pass down a function from the Board to the Square, and we'll have Square call that function when a square is clicked. We'll change the `renderSquare` method in Board to:

```javascript{5}
  renderSquare(i) {
    return (
      <Square
        value={this.state.squares[i]}
        onClick={() => this.handleClick(i)}
      />
    );
  }
```

>Note
>
>We split the returned element into multiple lines for readability, and added parentheses so that JavaScript doesn't insert a semicolon after `return` and break our code.

Now we're passing down two props from Board to Square: `value` and `onClick`. The `onClick` prop is a function that Square can call when clicked. We'll make the following changes to Square:

* Replace `this.state.value` with `this.props.value` in Square's `render` method
* Replace `this.setState()` with `this.props.onClick()` in Square's `render` method
* Delete the `constructor` from Square because Square no longer keeps track of the game's state

After these changes, the Square component looks like this:

```javascript{1,2,6,8}
class Square extends React.Component {
  render() {
    return (
      <button
        className="square"
        onClick={() => this.props.onClick()}
      >
        {this.props.value}
      </button>
    );
  }
}
```

When a Square is clicked, the `onClick` function provided by the Board is called. Here's a review of how this is achieved:

1. The `onClick` prop on the built-in DOM `<button>` component tells React to set up a click event listener.
2. When the button is clicked, React will call the `onClick` event handler that is defined in Square's `render()` method.
3. This event handler calls `this.props.onClick()`. The Square's `onClick` prop was specified by the Board.
4. Since the Board passed `onClick={() => this.handleClick(i)}` to Square, the Square calls `this.handleClick(i)` when clicked.
5. We have not defined the `handleClick()` method yet, so our code crashes. If you click a square now, you should see a red error screen saying something like "this.handleClick is not a function".

>Note
>
>The DOM `<button>` element's `onClick` attribute has a special meaning to React because it is a built-in component. For custom components like Square, the naming is up to you. We could give any name to the Square's `onClick` prop or Board's `handleClick` method, and the code would work the same. In React, it's conventional to use `on[Event]` names for props which represent events and `handle[Event]` for the methods which handle the events.

When we try to click a Square, we should get an error because we haven't defined `handleClick` yet. We'll now add `handleClick` to the Board class:

```javascript{9-13}
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
    };
  }

  handleClick(i) {
    const squares = this.state.squares.slice();
    squares[i] = 'X';
    this.setState({squares: squares});
  }

  renderSquare(i) {
    return (
      <Square
        value={this.state.squares[i]}
        onClick={() => this.handleClick(i)}
      />
    );
  }

  render() {
    const status = 'Next player: X';

    return (
      <div>
        <div className="status">{status}</div>
        <div className="board-row">
          {this.renderSquare(0)}
          {this.renderSquare(1)}
          {this.renderSquare(2)}
        </div>
        <div className="board-row">
          {this.renderSquare(3)}
          {this.renderSquare(4)}
          {this.renderSquare(5)}
        </div>
        <div className="board-row">
          {this.renderSquare(6)}
          {this.renderSquare(7)}
          {this.renderSquare(8)}
        </div>
      </div>
    );
  }
}
```

**[View the full code at this point](https://codepen.io/gaearon/pen/ybbQJX?editors=0010)**

After these changes, we're again able to click on the Squares to fill them, the same as we had before. However, now the state is stored in the Board component instead of the individual Square components. When the Board's state changes, the Square components re-render automatically. Keeping the state of all squares in the Board component will allow it to determine the winner in the future.

Since the Square components no longer maintain state, the Square components receive values from the Board component and inform the Board component when they're clicked. In React terms, the Square components are now **controlled components**. The Board has full control over them.

Note how in `handleClick`, we call `.slice()` to create a copy of the `squares` array to modify instead of modifying the existing array. We will explain why we create a copy of the `squares` array in the next section.

### Why Immutability Is Important {#why-immutability-is-important}

In the previous code example, we suggested that you use the `.slice()` method to create a copy of the `squares` array to modify instead of modifying the existing array. We'll now discuss immutability and why immutability is important to learn.

There are generally two approaches to changing data. The first approach is to *mutate* the data by directly changing the data's values. The second approach is to replace the data with a new copy which has the desired changes.

#### Data Change with Mutation {#data-change-with-mutation}
```javascript
var player = {score: 1, name: 'Jeff'};
player.score = 2;
// Now player is {score: 2, name: 'Jeff'}
```

#### Data Change without Mutation {#data-change-without-mutation}
```javascript
var player = {score: 1, name: 'Jeff'};

var newPlayer = Object.assign({}, player, {score: 2});
// Now player is unchanged, but newPlayer is {score: 2, name: 'Jeff'}

// Or if you are using object spread syntax proposal, you can write:
// var newPlayer = {...player, score: 2};
```

The end result is the same but by not mutating (or changing the underlying data) directly, we gain several benefits described below.

#### Complex Features Become Simple {#complex-features-become-simple}

Immutability makes complex features much easier to implement. Later in this tutorial, we will implement a "time travel" feature that allows us to review the tic-tac-toe game's history and "jump back" to previous moves. This functionality isn't specific to games -- an ability to undo and redo certain actions is a common requirement in applications. Avoiding direct data mutation lets us keep previous versions of the game's history intact, and reuse them later.

#### Detecting Changes {#detecting-changes}

Detecting changes in mutable objects is difficult because they are modified directly. This detection requires the mutable object to be compared to previous copies of itself and the entire object tree to be traversed.

Detecting changes in immutable objects is considerably easier. If the immutable object that is being referenced is different than the previous one, then the object has changed.

#### Determining When to Re-Render in React {#determining-when-to-re-render-in-react}

The main benefit of immutability is that it helps you build _pure components_ in React. Immutable data can easily determine if changes have been made which helps to determine when a component requires re-rendering.

You can learn more about `shouldComponentUpdate()` and how you can build *pure components* by reading [Optimizing Performance](/docs/optimizing-performance.html#examples).

### Function Components {#function-components}

We'll now change the Square to be a **function component**.

In React, **function components** are a simpler way to write components that only contain a `render` method and don't have their own state. Instead of defining a class which extends `React.Component`, we can write a function that takes `props` as input and returns what should be rendered. Function components are less tedious to write than classes, and many components can be expressed this way.

Replace the Square class with this function:

```javascript
function Square(props) {
  return (
    <button className="square" onClick={props.onClick}>
      {props.value}
    </button>
  );
}
```

We have changed `this.props` to `props` both times it appears.

**[View the full code at this point](https://codepen.io/gaearon/pen/QvvJOv?editors=0010)**

>Note
>
>When we modified the Square to be a function component, we also changed `onClick={() => this.props.onClick()}` to a shorter `onClick={props.onClick}` (note the lack of parentheses on *both* sides).

### Taking Turns {#taking-turns}

We now need to fix an obvious defect in our tic-tac-toe game: the "O"s cannot be marked on the board.

We'll set the first move to be "X" by default. We can set this default by modifying the initial state in our Board constructor:

```javascript{6}
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
      xIsNext: true,
    };
  }
```

Each time a player moves, `xIsNext` (a boolean) will be flipped to determine which player goes next and the game's state will be saved. We'll update the Board's `handleClick` function to flip the value of `xIsNext`:

```javascript{3,6}
  handleClick(i) {
    const squares = this.state.squares.slice();
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      squares: squares,
      xIsNext: !this.state.xIsNext,
    });
  }
```

With this change, "X"s and "O"s can take turns. Try it!

Let's also change the "status" text in Board's `render` so that it displays which player has the next turn:

```javascript{2}
  render() {
    const status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');

    return (
      // the rest has not changed
```

After applying these changes, you should have this Board component:

```javascript{6,11-16,29}
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
      xIsNext: true,
    };
  }

  handleClick(i) {
    const squares = this.state.squares.slice();
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      squares: squares,
      xIsNext: !this.state.xIsNext,
    });
  }

  renderSquare(i) {
    return (
      <Square
        value={this.state.squares[i]}
        onClick={() => this.handleClick(i)}
      />
    );
  }

  render() {
    const status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');

    return (
      <div>
        <div className="status">{status}</div>
        <div className="board-row">
          {this.renderSquare(0)}
          {this.renderSquare(1)}
          {this.renderSquare(2)}
        </div>
        <div className="board-row">
          {this.renderSquare(3)}
          {this.renderSquare(4)}
          {this.renderSquare(5)}
        </div>
        <div className="board-row">
          {this.renderSquare(6)}
          {this.renderSquare(7)}
          {this.renderSquare(8)}
        </div>
      </div>
    );
  }
}
```

**[View the full code at this point](https://codepen.io/gaearon/pen/KmmrBy?editors=0010)**

### Declaring a Winner {#declaring-a-winner}

Now that we show which player's turn is next, we should also show when the game is won and there are no more turns to make. Copy this helper function and paste it at the end of the file:

```javascript
function calculateWinner(squares) {
  const lines = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6],
  ];
  for (let i = 0; i < lines.length; i++) {
    const [a, b, c] = lines[i];
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
      return squares[a];
    }
  }
  return null;
}
```

Given an array of 9 squares, this function will check for a winner and return `'X'`, `'O'`, or `null` as appropriate.

We will call `calculateWinner(squares)` in the Board's `render` function to check if a player has won. If a player has won, we can display text such as "Winner: X" or "Winner: O". We'll replace the `status` declaration in Board's `render` function with this code:

```javascript{2-8}
  render() {
    const winner = calculateWinner(this.state.squares);
    let status;
    if (winner) {
      status = 'Winner: ' + winner;
    } else {
      status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
    }

    return (
      // the rest has not changed
```

We can now change the Board's `handleClick` function to return early by ignoring a click if someone has won the game or if a Square is already filled:

```javascript{3-5}
  handleClick(i) {
    const squares = this.state.squares.slice();
    if (calculateWinner(squares) || squares[i]) {
      return;
    }
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      squares: squares,
      xIsNext: !this.state.xIsNext,
    });
  }
```

**[View the full code at this point](https://codepen.io/gaearon/pen/LyyXgK?editors=0010)**

Congratulations! You now have a working tic-tac-toe game. And you've just learned the basics of React too. So *you're* probably the real winner here.

## Adding Time Travel {#adding-time-travel}

As a final exercise, let's make it possible to "go back in time" to the previous moves in the game.

### Storing a History of Moves {#storing-a-history-of-moves}

If we mutated the `squares` array, implementing time travel would be very difficult.

However, we used `slice()` to create a new copy of the `squares` array after every move, and [treated it as immutable](#why-immutability-is-important). This will allow us to store every past version of the `squares` array, and navigate between the turns that have already happened.

We'll store the past `squares` arrays in another array called `history`. The `history` array represents all board states, from the first to the last move, and has a shape like this:

```javascript
history = [
  // Before first move
  {
    squares: [
      null, null, null,
      null, null, null,
      null, null, null,
    ]
  },
  // After first move
  {
    squares: [
      null, null, null,
      null, 'X', null,
      null, null, null,
    ]
  },
  // After second move
  {
    squares: [
      null, null, null,
      null, 'X', null,
      null, null, 'O',
    ]
  },
  // ...
]
```

Now we need to decide which component should own the `history` state.

### Lifting State Up, Again {#lifting-state-up-again}

We'll want the top-level Game component to display a list of past moves. It will need access to the `history` to do that, so we will place the `history` state in the top-level Game component.

Placing the `history` state into the Game component lets us remove the `squares` state from its child Board component. Just like we ["lifted state up"](#lifting-state-up) from the Square component into the Board component, we are now lifting it up from the Board into the top-level Game component. This gives the Game component full control over the Board's data, and lets it instruct the Board to render previous turns from the `history`.

First, we'll set up the initial state for the Game component within its constructor:

```javascript{2-10}
class Game extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      history: [{
        squares: Array(9).fill(null),
      }],
      xIsNext: true,
    };
  }

  render() {
    return (
      <div className="game">
        <div className="game-board">
          <Board />
        </div>
        <div className="game-info">
          <div>{/* status */}</div>
          <ol>{/* TODO */}</ol>
        </div>
      </div>
    );
  }
}
```

Next, we'll have the Board component receive `squares` and `onClick` props from the Game component. Since we now have a single click handler in Board for many Squares, we'll need to pass the location of each Square into the `onClick` handler to indicate which Square was clicked. Here are the required steps to transform the Board component:

* Delete the `constructor` in Board.
* Replace `this.state.squares[i]` with `this.props.squares[i]` in Board's `renderSquare`.
* Replace `this.handleClick(i)` with `this.props.onClick(i)` in Board's `renderSquare`.

The Board component now looks like this:

```javascript{17,18}
class Board extends React.Component {
  handleClick(i) {
    const squares = this.state.squares.slice();
    if (calculateWinner(squares) || squares[i]) {
      return;
    }
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      squares: squares,
      xIsNext: !this.state.xIsNext,
    });
  }

  renderSquare(i) {
    return (
      <Square
        value={this.props.squares[i]}
        onClick={() => this.props.onClick(i)}
      />
    );
  }

  render() {
    const winner = calculateWinner(this.state.squares);
    let status;
    if (winner) {
      status = 'Winner: ' + winner;
    } else {
      status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
    }

    return (
      <div>
        <div className="status">{status}</div>
        <div className="board-row">
          {this.renderSquare(0)}
          {this.renderSquare(1)}
          {this.renderSquare(2)}
        </div>
        <div className="board-row">
          {this.renderSquare(3)}
          {this.renderSquare(4)}
          {this.renderSquare(5)}
        </div>
        <div className="board-row">
          {this.renderSquare(6)}
          {this.renderSquare(7)}
          {this.renderSquare(8)}
        </div>
      </div>
    );
  }
}
```

We'll update the Game component's `render` function to use the most recent history entry to determine and display the game's status:

```javascript{2-11,16-19,22}
  render() {
    const history = this.state.history;
    const current = history[history.length - 1];
    const winner = calculateWinner(current.squares);

    let status;
    if (winner) {
      status = 'Winner: ' + winner;
    } else {
      status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
    }

    return (
      <div className="game">
        <div className="game-board">
          <Board
            squares={current.squares}
            onClick={(i) => this.handleClick(i)}
          />
        </div>
        <div className="game-info">
          <div>{status}</div>
          <ol>{/* TODO */}</ol>
        </div>
      </div>
    );
  }
```

Since the Game component is now rendering the game's status, we can remove the corresponding code from the Board's `render` method. After refactoring, the Board's `render` function looks like this:

```js{1-4}
  render() {
    return (
      <div>
        <div className="board-row">
          {this.renderSquare(0)}
          {this.renderSquare(1)}
          {this.renderSquare(2)}
        </div>
        <div className="board-row">
          {this.renderSquare(3)}
          {this.renderSquare(4)}
          {this.renderSquare(5)}
        </div>
        <div className="board-row">
          {this.renderSquare(6)}
          {this.renderSquare(7)}
          {this.renderSquare(8)}
        </div>
      </div>
    );
  }
```

Finally, we need to move the `handleClick` method from the Board component to the Game component. We also need to modify `handleClick` because the Game component's state is structured differently. Within the Game's `handleClick` method, we concatenate new history entries onto `history`.

```javascript{2-4,10-12}
  handleClick(i) {
    const history = this.state.history;
    const current = history[history.length - 1];
    const squares = current.squares.slice();
    if (calculateWinner(squares) || squares[i]) {
      return;
    }
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      history: history.concat([{
        squares: squares,
      }]),
      xIsNext: !this.state.xIsNext,
    });
  }
```

>Note
>
>Unlike the array `push()` method you might be more familiar with, the `concat()` method doesn't mutate the original array, so we prefer it.

At this point, the Board component only needs the `renderSquare` and `render` methods. The game's state and the `handleClick` method should be in the Game component.

**[View the full code at this point](https://codepen.io/gaearon/pen/EmmOqJ?editors=0010)**

### Showing the Past Moves {#showing-the-past-moves}

Since we are recording the tic-tac-toe game's history, we can now display it to the player as a list of past moves.

We learned earlier that React elements are first-class JavaScript objects; we can pass them around in our applications. To render multiple items in React, we can use an array of React elements.

In JavaScript, arrays have a [`map()` method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) that is commonly used for mapping data to other data, for example:

```js
const numbers = [1, 2, 3];
const doubled = numbers.map(x => x * 2); // [2, 4, 6]
```

Using the `map` method, we can map our history of moves to React elements representing buttons on the screen, and display a list of buttons to "jump" to past moves.

Let's `map` over the `history` in the Game's `render` method:

```javascript{6-15,34}
  render() {
    const history = this.state.history;
    const current = history[history.length - 1];
    const winner = calculateWinner(current.squares);

    const moves = history.map((step, move) => {
      const desc = move ?
        'Go to move #' + move :
        'Go to game start';
      return (
        <li>
          <button onClick={() => this.jumpTo(move)}>{desc}</button>
        </li>
      );
    });

    let status;
    if (winner) {
      status = 'Winner: ' + winner;
    } else {
      status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
    }

    return (
      <div className="game">
        <div className="game-board">
          <Board
            squares={current.squares}
            onClick={(i) => this.handleClick(i)}
          />
        </div>
        <div className="game-info">
          <div>{status}</div>
          <ol>{moves}</ol>
        </div>
      </div>
    );
  }
```

**[View the full code at this point](https://codepen.io/gaearon/pen/EmmGEa?editors=0010)**

For each move in the tic-tac-toe game's history, we create a list item `<li>` which contains a button `<button>`. The button has a `onClick` handler which calls a method called `this.jumpTo()`. We haven't implemented the `jumpTo()` method yet. For now, we should see a list of the moves that have occurred in the game and a warning in the developer tools console that says:

>  Warning:
>  Each child in an array or iterator should have a unique "key" prop. Check the render method of "Game".

Let's discuss what the above warning means.

### Picking a Key {#picking-a-key}

When we render a list, React stores some information about each rendered list item. When we update a list, React needs to determine what has changed. We could have added, removed, re-arranged, or updated the list's items.

Imagine transitioning from

```html
<li>Alexa: 7 tasks left</li>
<li>Ben: 5 tasks left</li>
```

to

```html
<li>Ben: 9 tasks left</li>
<li>Claudia: 8 tasks left</li>
<li>Alexa: 5 tasks left</li>
```

In addition to the updated counts, a human reading this would probably say that we swapped Alexa and Ben's ordering and inserted Claudia between Alexa and Ben. However, React is a computer program and does not know what we intended. Because React cannot know our intentions, we need to specify a *key* property for each list item to differentiate each list item from its siblings. One option would be to use the strings `alexa`, `ben`, `claudia`. If we were displaying data from a database, Alexa, Ben, and Claudia's database IDs could be used as keys.

```html
<li key={user.id}>{user.name}: {user.taskCount} tasks left</li>
```

When a list is re-rendered, React takes each list item's key and searches the previous list's items for a matching key. If the current list has a key that didn't exist before, React creates a component. If the current list is missing a key that existed in the previous list, React destroys the previous component. If two keys match, the corresponding component is moved. Keys tell React about the identity of each component which allows React to maintain state between re-renders. If a component's key changes, the component will be destroyed and re-created with a new state.

`key` is a special and reserved property in React (along with `ref`, a more advanced feature). When an element is created, React extracts the `key` property and stores the key directly on the returned element. Even though `key` may look like it belongs in `props`, `key` cannot be referenced using `this.props.key`. React automatically uses `key` to decide which components to update. A component cannot inquire about its `key`.

**It's strongly recommended that you assign proper keys whenever you build dynamic lists.** If you don't have an appropriate key, you may want to consider restructuring your data so that you do.

If no key is specified, React will present a warning and use the array index as a key by default. Using the array index as a key is problematic when trying to re-order a list's items or inserting/removing list items. Explicitly passing `key={i}` silences the warning but has the same problems as array indices and is not recommended in most cases.

Keys do not need to be globally unique; they only need to be unique between components and their siblings.


### Implementing Time Travel {#implementing-time-travel}

In the tic-tac-toe game's history, each past move has a unique ID associated with it: it's the sequential number of the move. The moves are never re-ordered, deleted, or inserted in the middle, so it's safe to use the move index as a key.

In the Game component's `render` method, we can add the key as `<li key={move}>` and React's warning about keys should disappear:

```js{6}
    const moves = history.map((step, move) => {
      const desc = move ?
        'Go to move #' + move :
        'Go to game start';
      return (
        <li key={move}>
          <button onClick={() => this.jumpTo(move)}>{desc}</button>
        </li>
      );
    });
```

**[View the full code at this point](https://codepen.io/gaearon/pen/PmmXRE?editors=0010)**

Clicking any of the list item's buttons throws an error because the `jumpTo` method is undefined. Before we implement `jumpTo`, we'll add `stepNumber` to the Game component's state to indicate which step we're currently viewing.

First, add `stepNumber: 0` to the initial state in Game's `constructor`:

```js{8}
class Game extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      history: [{
        squares: Array(9).fill(null),
      }],
      stepNumber: 0,
      xIsNext: true,
    };
  }
```

Next, we'll define the `jumpTo` method in Game to update that `stepNumber`. We also set `xIsNext` to true if the number that we're changing `stepNumber` to is even:

```javascript{5-10}
  handleClick(i) {
    // this method has not changed
  }

  jumpTo(step) {
    this.setState({
      stepNumber: step,
      xIsNext: (step % 2) === 0,
    });
  }

  render() {
    // this method has not changed
  }
```

We will now make a few changes to the Game's `handleClick` method which fires when you click on a square.

The `stepNumber` state we've added reflects the move displayed to the user now. After we make a new move, we need to update `stepNumber` by adding `stepNumber: history.length` as part of the `this.setState` argument. This ensures we don't get stuck showing the same move after a new one has been made.

We will also replace reading `this.state.history` with `this.state.history.slice(0, this.state.stepNumber + 1)`. This ensures that if we "go back in time" and then make a new move from that point, we throw away all the "future" history that would now become incorrect.

```javascript{2,13}
  handleClick(i) {
    const history = this.state.history.slice(0, this.state.stepNumber + 1);
    const current = history[history.length - 1];
    const squares = current.squares.slice();
    if (calculateWinner(squares) || squares[i]) {
      return;
    }
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      history: history.concat([{
        squares: squares
      }]),
      stepNumber: history.length,
      xIsNext: !this.state.xIsNext,
    });
  }
```

Finally, we will modify the Game component's `render` method from always rendering the last move to rendering the currently selected move according to `stepNumber`:

```javascript{3}
  render() {
    const history = this.state.history;
    const current = history[this.state.stepNumber];
    const winner = calculateWinner(current.squares);

    // the rest has not changed
```

If we click on any step in the game's history, the tic-tac-toe board should immediately update to show what the board looked like after that step occurred.

**[View the full code at this point](https://codepen.io/gaearon/pen/gWWZgR?editors=0010)**

### Wrapping Up {#wrapping-up}

Congratulations! You've created a tic-tac-toe game that:

* Lets you play tic-tac-toe,
* Indicates when a player has won the game,
* Stores a game's history as a game progresses,
* Allows players to review a game's history and see previous versions of a game's board.

Nice work! We hope you now feel like you have a decent grasp on how React works.

Check out the final result here: **[Final Result](https://codepen.io/gaearon/pen/gWWZgR?editors=0010)**.

If you have extra time or want to practice your new React skills, here are some ideas for improvements that you could make to the tic-tac-toe game which are listed in order of increasing difficulty:

1. Display the location for each move in the format (col, row) in the move history list.
2. Bold the currently selected item in the move list.
3. Rewrite Board to use two loops to make the squares instead of hardcoding them.
4. Add a toggle button that lets you sort the moves in either ascending or descending order.
5. When someone wins, highlight the three squares that caused the win.
6. When no one wins, display a message about the result being a draw.

Throughout this tutorial, we touched on React concepts including elements, components, props, and state. For a more detailed explanation of each of these topics, check out [the rest of the documentation](/docs/hello-world.html). To learn more about defining components, check out the [`React.Component` API reference](/docs/react-component.html).
