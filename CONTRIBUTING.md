# Contribution to Open-Beta's Open-Taco Project

---------------

## Index of Contributing.md

  |Title of Work done | Link to that section |
 |----------|------------|
 | About Project  | [Scroll to About project](#about-the-project) |
 | Fork of the Project | [Scroll to Fork](#fork-of-the-project) | 
 | Links to the external community |   [Scroll to Links](#links-to-the-external-community-and-project) |                          
 | Issues that I will be working on |   [Scroll to issues](#issues-that-i-will-be-working-on) | 
| Compiling open-tacos project | [Scroll to compilation](#compiling-open-tacos-project) |
 | Issue 1 |   [Scroll to issue 1](#issue-1) |
 | Work done for issue 1 | [Scroll to work done for issue 1](#working-on-issue-1)
 | Issue 2 |   [Scroll to issue 2](#issue-2) |
 | Work done for issue 2 | [Scroll to work done for issue 2](#work-done-in-solving-this-issue) |
 | Reflection on Success| [Scroll to reflection](#reflection-on-success)|
 | Discussion of next steps| [Scroll to discussion](#discussion-of-next-steps)|


## Project Name: Open-tacos

---

## About the project

[Open-Tacos](https://github.com/OpenBeta/open-tacos/tree/develop) is one of the main work done by the [Open Beta](https://github.com/OpenBeta) organization, where many contributors came together to make a platform for rock climbing enthusiasts. It is an open source project and is in its late development stage; some versions of this project have already been published, and the live website can be found [here](https://openbeta.io/) . The main tech stack of the project is GraphQL, Typescript, React, MongoDB, and Node.js. I am pretty familiar with all the tech used here, and the repository has tens of issues open, which will be good to explore and resolve. The repository can be found [here](https://github.com/OpenBeta/open-tacos).

---

## Fork of the Project

I forked the development branch of the project, and it can be found [here](https://github.com/YogeshManni/open-tacos).

---

## Links to the external community and project

**Link to project** - [open-tacos](https://github.com/OpenBeta/open-tacos/tree/develop?tab=readme-ov-file)

**Link to Discord community** - [open-beta discord server](https://discord.com/invite/ptpnWWNkJx)

**Link to graphql-backend** - [openbeta-graphql](https://github.com/OpenBeta/openbeta-graphql)

---

## Issues that I will be working on: 

--------------------------

### Issue 1

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

<br>

*Kim T, "How to run Next Js application build", stackoverflow.com, 03 Dec. 2021, [Run NextJs](https://stackoverflow.com/questions/63518597/how-to-run-next-js-application-build-out-directory)*


<br>
<br>

_Below is some images of successful compilation of project._

### VS code successful compilation

<img width="959" alt="image" src="https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/bbf1c9f2-5cb3-46bc-90a7-fb775967e3e6">

### Website running on localhost:3000 server

<img width="1910" alt="image" src="https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/346dace2-c819-41bb-9b73-0bfebb5047d5">

---

## Working on issue 1

After compiling my project, I started working to edit react files to solve the header width issue. As I dived deep into the workflow and folder structure of the application, I came to know that they have designed three headers instead of one. First header component is for Mobile View, second one is for Desktop and larger screens, and third is also for desktop but thats for their promotion and about pages.

For this issue, I had to correct mobile header and desktop header for main content as per the issue. In the project, developers are using tailwind for styling website which I am already familiar with. The first change I made was to add max-width to 7xl for extra large screen, which will align header to the rest of website content. Below given are the changes that I have made -

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

<br>

*Tailwind Labs, "Tailwind Max-widths", tailwindcss.com, March 2024, [Tailwind Max Widths](https://tailwindcss.com/docs/max-width)*

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

<br>

*React, "Your first component", react.dev, March 2024, [React components](https://react.dev/learn/your-first-component)*

<br>

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

--------------------------

## Issue 2

--------------------------
  After solving First issue, I started working on second issue that I was interested in resolving.  The issue is as follows - 

  When a user logout from the website and then if he go to any area or location and try to edit something then the user will stuck in an infinite loop of page reloading (Page keep on loading infinitely).
  Full issue can be seen [here](https://github.com/OpenBeta/open-tacos/issues/856)

  **Expected behaviour** - The user proposal is to disable the edit button if he's not logged in.

  ------------------------

  ## Labels associated with the issue are :

  - bug

  **Date issue reported** : June 2, 2023 

  -------------------------

  ## Why I decided to work on this issue

  This issue was related to frontend correction with some user authentication conditions. I am quite familiar with react that is used as frontend here and by now I understand the workflow of project which makes it easier for me to resolve this issue.

  --------------------------

   ## Work done in solving this issue 

   **Following steps were taken to resolve this issue :**

   ### Step 1
   
   To resolve this issue firstly I had to check about user's session that if user is currently logged in or not. For that I used `next-auth` react module which developers were already using in the project to fetch user's session. In [AreaPageActions](https://github.com/YogeshManni/open-tacos/blob/6a9713c62b2137d7123a8953723ebff6f86e8646/src/app/(default)/components/AreaPageActions.tsx) file I imported the `next-auth` module to get user session. It was imported as given below - 

   ```javascript
      import { signIn, useSession } from 'next-auth/react'
   ```

  After that I had to include `client` namespace in the component so I can fetch the user session properly without any error. This was imnported as  - 

  ```javascript
      'use client'
   ```

  ### Step 2 

  After successfully importing needed modules I had to create `status` variable to fetch the current user's session. For that I used `useSession` hook that is available in `next-auth` module.

  ```javascript
      const { status } = useSession() 
  ```

  Use session hook provides us with three status which are - 

  - authenticated
  - loading
  - unauthenticated

   I will use this status variable in Step 3 to find out if user is logged in or not.

   ### Step 3

  After status was fetched successfully from `useSession` hook, I used conditional operator in Edit button class to disable it. It was done as as given below - 

 ```javascript

   <Link href={`/editArea/${uuid}`} target='_new' className={`btn btn-solid btn-accent shadow-md ${status === 'unauthenticated' && 'pointer-events-none opacity-50'}`}>
      <PencilSimple size={20} weight='duotone' /> Edit
    </Link>

 ```

  **Explanation** - Above you can see, in `className` I used `status` variable to check if the user is logged in or not. So I added `pointer-events-none` and `opacity-50` classes to disable the button
  if status is `unauthenticated`. By doing so user won't be able to click edit button when not logged in, hence avoiding getting stuck in infinite loop.


  ### Step 4

  Same as edit button, there was `Photo` button next to `Edit` button which was causing the same problem so I had to disable that as well. For that I had to pass already fetched `status` variable as props to [UploadPhotoButton](https://github.com/YogeshManni/open-tacos/blob/develop/src/components/media/PhotoUploadButtons.tsx) component as there was a separate component for Upload photo button. So I made the following changes in files - 

 In  [AreaPageActions](https://github.com/YogeshManni/open-tacos/blob/6a9713c62b2137d7123a8953723ebff6f86e8646/src/app/(default)/components/AreaPageActions.tsx) I passed status to `UploadPhotoButton` component -

 ```javascript

   <UploadPhotoButton status= {status}/>

 ```
 Then in [PhotoUpload](https://github.com/YogeshManni/open-tacos/blob/develop/src/components/media/PhotoUploadButtons.tsx) component I fetched the status variable as incoming prop's parameter.

```javascript

   export const UploadPhotoButton: React.FC<{status:string}> = ({status}) => (
  }

 ```

### Step 5

  Finally I had to add the same status condition here as well to disable the Photo button. So I added conditional check in `className` to check if user is authenticated or not and added same `pointer-events-none` and ` opacity-50` classes. It was done as follows - 
 
  ```javascript

  export const UploadPhotoButton: React.FC<{status:string}> = ({status}) => (

  <BaseUploaderWithNext13Context className={`btn ${status === 'unauthenticated' && 'pointer-events-none opacity-50'}`}>

    <Camera size={20} /> <span className='hidden md:inline'>Photo</span>

  </BaseUploaderWithNext13Context>

)

 ```
<br>

*React, "Your first component", react.dev, March 2024, [React components](https://react.dev/learn/your-first-component)*

*Open Beta, "Open beta Climbing catalog", openbeta.io, Feb 2024, [Open-tacos Project](https://github.com/OpenBeta/open-tacos)*

<br>
---------------------

 ## Before and After applying fix


### Before Fix

   Before I solved this issue, the buttons were enabled even the user was logged out and were appearing as shown in the image below. This issue is still not fixed on the official website so we can see the button enabled there as well. From [here](http://localhost:3000/area/2a40e704-cca6-5cd0-8b7d-404654e65186/lynn-woods) we can see the buttons enabled even loged out.

<img width="1028" alt="image" src="https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/fb006aa5-589c-4b5e-967e-8a3418879e79">

### After Fix

  After adding necessary classes and code in [AreaPageActions](https://github.com/YogeshManni/open-tacos/blob/6a9713c62b2137d7123a8953723ebff6f86e8646/src/app/(default)/components/AreaPageActions.tsx) and  [PhotoUpload](https://github.com/YogeshManni/open-tacos/blob/develop/src/components/media/PhotoUploadButtons.tsx) components, both buttons were disabled when user is logged out. We can see buttons are grayscaled a bit in image below as they are disabled.

<img width="1028" alt="image" src="https://github.com/nic-dgl104-winter-2024/rrj-YogeshManni/assets/29475936/bba64a6e-3dc9-4061-969f-aab8b3a7f488">

-----------------------

## Reflection on Success

  I was able to successfully solve both the issues that I took. I was very familiar with the framework and workflow of open-tacos project that really helped me solving the issues. There were no such hard roadblocks faced in development process, however while compiling project it failed couple of times, but with the help of error outputs I solved them one by one and compiled the project successfully. The main errors that came during compilation were - 
  
  - Npm packages were missing
  - Needed to downgrade Node version
  - Graphql packages were missing (However this is not required to run the frontend)

I solved these errors by downgrading my node version and then installing the missing packages with the following command.

```
npm install
```

Graphql can be installed by using the below command, but its not necessary to run the project.

```
npm install graphql --save
```

<br>

*GraphQl, "GraphQl Getting started", graphql.org, March 28. 2024, [Graphql prerequisites](https://graphql.org/graphql-js/)*

<br>
------------------------------

## Discussion of next steps

  For next steps, I will probably propose the changes that I have made for solving [issue#2](#issue-2) to the official [Open-tacos](https://github.com/OpenBeta/open-tacos/tree/develop) repository.
  Also while solving issue#2, I found some more bugs that are not yet listed as issues in the official repository of open-tacos. So I will report them to the contributors there so they can review and check if someone is 
  working on it or not and hopefully solve them too. I learned a lot from this project and very much interested in working more and be a contributor of [Open-beta](https://github.com/OpenBeta) community.Their tech stack is great and I would like to learn more about Graphql and Next.js.

---------------------------


[Scroll to Top](#contribution-to-open-betas-open-taco-project)
  
    
  

  
  
