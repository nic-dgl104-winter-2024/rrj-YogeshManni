# Contribution to Open-Beta's Open-Taco Project

## Project Name: Open-tacos

---

## About the project

[Open-Tacos](https://github.com/OpenBeta/open-tacos/tree/develop) is one of the main works done by the [Open Beta](https://github.com/OpenBeta) organization, where a lot of contributors came together to make a platform for rock climbing enthusiasts. It is an open source project and is in its late development stage; some versions of this project have already been published, and the live website can be found at [here](https://openbeta.io/) . The main tech stack of the project is GraphQL, Typescript, React, MongoDB, and Node.js. I am pretty familiar with all the tech used here, and the repository has tens of issues open, which will be good to explore and resolve. The repository can be found [here](https://github.com/OpenBeta/open-tacos).

---

## Fork of the project

I forked the development branch of the project, and it can be found [here](https://github.com/YogeshManni/open-tacos).

---

## Links to the external community and project

**Link to project** - [open-tacos](https://github.com/OpenBeta/open-tacos/tree/develop?tab=readme-ov-file)

**Link to Discord community** - [open-beta discord server](https://discord.com/invite/ptpnWWNkJx)

**Link to grpahql-backend** - [openbeta-graphql](https://github.com/OpenBeta/openbeta-graphql)

---

## Issues that I will be working on: 

On the Open-Tacos website, the header part is not aligned with the content; the header is narrower than the rest of the content on the page. This results in multiple distinct widths that users and developers want to avoid. I will be fixing the header width for all the platforms so it can align with the main content. The issue reported can be found at [Content width issue](https://github.com/OpenBeta/open-tacos/issues/1096).

---

## Labels associated with the issue are: 

- good first
- issueHelp wanted

**Date issue reported**: February 13, 2024

**Date issue closed** : 25th March,2024 (I completed my work and resolved this issue on my forked repository by 18th March, 2024. However it got closed on the official repository by some other contributor on 25th March,2024)

---

## Why I decided to work on this issue

I picked this project because of the tech stack that is being used to develop it. I have built several projects before using React, Node.js. Typescript and GraphQl, so it will be easy to understand the code and work on it.

The issue I will be resolving is related to the frontend of the project, where the width of the header container needs to be fixed so it will align with the content and be flexible enough to match the content on all platforms. I am very familiar with frontend technology and have been working with CSS, HTML, JS, and React for a while now, so I know what approaches can be taken to fix the issue.

---

## Work started on project to fix the issue

### Compiling open-tacos project

After forking [open-tacos](https://github.com/YogeshManni/open-tacos) repository, I started compiling it. There were lot of errors in start such as node module errors, some dependencies and formatting issues. I read the documentation of project and that was somewhat helpful in fixing some errors, then I installed all the missing modules using following command.

```
npm install
```

Finally the project was compiled and ran using below command.

```
npm run dev
```

_Below is some images of successfull compilation of project._

### VS code successfull compilation

<img width="959" alt="image" src="https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/bbf1c9f2-5cb3-46bc-90a7-fb775967e3e6">

### Website running on localhost:3000 server

<img width="1910" alt="image" src="https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/346dace2-c819-41bb-9b73-0bfebb5047d5">

---

## Working on issue

After compiling my project, I started working to edit react files to solve the header width issue. As I dived deep into the workflow and folder structure of the application, I came to know that they have designed three headers instead of one. First header component is for Mobile View, second one is for Desktop and larger screens, and third is also for desktop but thats for their promotion and about pages.

For this issue, I had to correct mobile header and dekstop header for main content as per the issue. In thi project, developers are using tailwind for styling website which I am already familiar with. The first change I made was to add max-width to 7xl for extra large screen, which will align header to the rest of website content. Below given are the changes that I have made -

```javascript

export default async function Header (): Promise<any> {
return (
  <div className='max-w-5xl xl:max-w-7xl mx-auto px-4 xl:px-0'>
     <DesktopHeader />	      <DesktopHeader />
     <MobileHeader />	      <MobileHeader />
   </div>
 ))
}

```

In above code I added `xl:max-w-7xl` to the class, which means to set width of header to `7xl(80 rem)` for large screens.

I have added an image below from tailwind official documentation to get better understanding of different type of widths in utility classes.

![image](https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/7bc9540c-a297-4a83-aa55-2b258bcb565c)

---

## Result of this fix -

_Before adding class_ - As you can see in image below header is not at all aligning with the page content.

![image](https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/8e476031-3db1-42e4-b4b2-e42f7af4903e)

_After applying max-width fix_ - After adding max-width for extra large screen, header is perfectly aligning with content as shown in image below.

![image](https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/a7dafad5-181b-49fa-bd34-e0034c4d552f)

---

## Changing Latest photo section

On the website [Main page](https://openbeta.io/) we can see the latest photo section is also not aligning with the content. In the issue the user wants only map to be of full width, rest everything should align with the content to eradicate different widths for frontend simplification.

To correct this issue, I used the same class `xl:max-w-7xl` to align the width with website content in [RecentTag.tsx](<https://github.com/YogeshManni/open-tacos/blob/develop/src/app/(default)/components/RecentTags.tsx>) component.

```javascript
return (
  <section className="w-full xl:max-w-7xl">
    <div className="px-4 2xl:px-0 mx-auto max-w-5xl xl:max-w-7xl">
      <h2>Latest Photos</h2>
    </div>
  </section>
);
```

In the above code I added `xl:max-w-7xl` in addition to `w-full` class to align photos section with other content.

But after this the result was not the same as I expected, the photos section was moved to left of screen, so I had to center it by adding an additional class.

I added `xl:mx-auto` to center the photos section. What this class does is that it applies sets the left and right margins to auto, resulting in centering the section. So the whole class became -

```javascript
return (
  <section className="w-full xl:max-w-7xl xl:mx-auto">
    <div className="px-4 2xl:px-0 mx-auto max-w-5xl xl:max-w-7xl">
      <h2>Latest Photos</h2>
    </div>
  </section>
);
```

After this change photos section was perfect for desktop view, but when I tested it in Mobile view it was not aligning with content, there was no padding and photos section was getting full width on mobile which added a horizontal scroll to website in mobile view.

To fix this issue, I added `px-4 xl:px-0` classes which means to add `4 rem` padding on small, medium and large screens and `0 rem` padding on extra large screens. Additionally I had to remove `w-full` class which was giving full width to the photos section that we didn't want. So i replaced it with `max-w-5xl` which means to give it width of `64 rem` till the large screens.

Finally the component class looked like below -

```javascript
return (
  <section className="max-w-5xl xl:max-w-7xl mx-auto px-4 xl:px-0">
    <div className="px-4 2xl:px-0 mx-auto max-w-5xl xl:max-w-7xl">
      <h2>Latest Photos</h2>
    </div>
  </section>
);
```

---

## Result of fix

_Before the addition of max-width classes_ - The latest photos section is covering the whole area and is not aligned with the content.

_Large screen view_

![image](https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/12081d61-3b8e-4a97-aedb-6bc5e49f666b)

_Small screen View_

![image](https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/8ff51284-80a0-4343-b9e0-256d7283f8fc)

_After the addition of max-width classes_ - The latest photos section is perfectly aligned with the content.

_Large screen view_

![image](https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/d7cbae0d-14a0-4c2e-9926-7329748d3986)

_Small screen View_

![image](https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/1ca043a6-bff5-455b-a0b9-470a8f89dfbe)
