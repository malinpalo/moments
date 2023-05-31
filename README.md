# TribeHub

<p align="center">
    <img src="readme_assets/amiresponsive.png" width=600>
</p>
<p align="center">
    Image generated using <a href="https://ui.dev/amiresponsive" target="_blank">https://ui.dev/amiresponsive</a>
</p>

## Project goals
Gro is social network plattform designed for plant loving users mainly in Sweden. 
The primary goals of the web app are to:

1) Provide likasinnade a place to meet up on the net to share thoughts, ideas and knowledge about plants and gardening.

As a visitor you can also search for the plants by the plants type in case you are looking for an epecific plant one.

Users of the site can register on the website to access all the features of the website. Such as liking your favourite posts as well as following certain users in order to be aware of what they will post in the future.

2) Deliver a simple and intuitive user experience, suitable for users in all ages. 

3) Offer a minimal set of features chosen in order to deliver a useful application within an achievable development timeframe, while laying a foundation for additional features in the future.

This is the repository for the React frontend of Gro.
The project also utilises a Django Rest Framework web API, the repository that you can find [here](https://github.com/andy-guttridge/tribehub_drf).


## Table of contents
- [Gro](#gro)
  * [Project goals](#project-goals)
  * [Table of content](#table-of-content)
  * [User stories](#user-stories)
    + [Themes](#themes)
    + [Epics](#epics)
    + [User stories](#user-stories-1)
  * [Agile development methodology](#agile-development-methodology)
  * [Planning](#planning)
    + [Mockups](#mockups)
    + [Data models](#data-models)
  * [Design](#design)
    + [Colours](#colours)
    + [Fonts](#fonts)
  * [Features](#features)
    + [Landing page with hero image](#landing-page-with-hero-image)
    + [Registration form](#registration-form)
    + [Sign-in form](#sign-in-form)
    + [Header with welcome message, notifications menu and sign-out button](#header-with-welcome-message--notifications-menu-and-sign-out-button)
    + [Bottom navbar](#bottom-navbar)
    + [Drop-down notifications menu](#drop-down-notifications-menu)
    + [Home page with family calendar](#home-page-with-family-calendar)
    + [Add event and search buttons](#add-event-and-search-buttons)
    + [Calendar events detail displayed below calendar](#calendar-events-detail-displayed-below-calendar)
    + [Edit event and delete event buttons](#edit-event-and-delete-event-buttons)
    + [Add event form](#add-event-form)
    + [Edit event form](#edit-event-form)
    + [Family contacts page](#family-contacts-page)
    + [Add contacts and search contacts buttons](#add-contacts-and-search-contacts-buttons)
    + [Add contact form](#add-contact-form)
    + [Search contacts form](#search-contacts-form)
    + [Edit contact and delete contact buttons](#edit-contact-and-delete-contact-buttons)
    + [Edit contact form](#edit-contact-form)
    + [Account page with My Tribe, My Profile, Change Password and Delete Account](#account-page-with-my-tribe--my-profile--change-password-and-delete-account)
    + [My Tribe](#my-tribe)
    + [My Profile](#my-profile)
    + [Change password](#change-password)
    + [Delete account](#delete-account)
    + [Modal dialogs to confirm or cancel destructive actions](#modal-dialogs-to-confirm-or-cancel-destructive-actions)
    + ['Single page mode' for medium and large screen sizes](#-single-page-mode--for-medium-and-large-screen-sizes)
    + [Prompts for new users](#prompts-for-new-users)
    + [Success messages](#success-messages)
    + [Error messages](#error-messages)
    + [Darkmode](#darkmode)
    + [Re-use of components](#re-use-of-components)
      - [`Avatar.js`](#-avatarjs-)
      - [`ConfirmModal.js`](#-confirmmodaljs-)
      - [`NotificationItem.js`](#-notificationitemjs-)
      - [`Spinner.js`](#-spinnerjs-)
      - [`Account.js`](#-accountjs-)
      - [`TribeMember.js`](#-tribememberjs-)
      - [`Contacts.js`](#-contactsjs-)
      - [`Contact.js`](#-contactjs-)
      - [`ContactDetailsForm.js`](#-contactdetailsformjs-)
      - [`CalEvent.js`](#-caleventjs-)
      - [`EventDetailsForm.js`](#-eventdetailsformjs-)
    + [CRUD functionality](#crud-functionality)
    + [Future improvements and features](#future-improvements-and-features)
      - [Short term future improvements](#short-term-future-improvements)
      - [Longer term future features](#longer-term-future-features)
  * [Frameworks, libraries and dependencies](#frameworks--libraries-and-dependencies)
    + [React-Calendar](#react-calendar)
    + [React-Router-DOM](#react-router-dom)
    + [ReactDOM](#reactdom)
    + [Axios](#axios)
    + [JWT Decode](#jwt-decode)
    + [Tailwind CSS](#tailwind-css)
    + [daisyUI](#daisyui)
    + [React Bootstrap Icons](#react-bootstrap-icons)
  * [React features used to enhance user experience](#react-features-used-to-enhance-user-experience)
    + [Custom hooks](#custom-hooks)
  * [Testing](#testing)
    + [Manual testing](#manual-testing)
    + [Validator testing](#validator-testing)
    + [W3C CSS validator](#w3c-css-validator)
    + [ESLint JavaScript validator](#eslint-javascript-validator)
    + [WAVE web accessability testing](#wave-web-accessability-testing)
    + [Lighthouse testing](#lighthouse-testing)
    + [Resolved bugs](#resolved-bugs)
    + [Unresolved bugs](#unresolved-bugs)
  * [Deployment](#deployment)
    + [Forking the GitHub Repository](#forking-the-github-repository)
    + [Making a Local Clone](#making-a-local-clone)
    + [Deploying with Heroku](#deploying-with-heroku)
  * [Credits](#credits)
    + [Code](#code)
    + [Media](#media)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


## User stories
Themes, epics, user stories and testing outcomes are documented in the `user_stories` .

### Themes
Themes were developed using the project goals as a starting point. These included:

- Account management - necessary to support the use of the app on an individual basis and to group users together into a 'tribe' to support goal 1.
- Calendar/event scheduling - essential to enable the key functionality required by goal 1.
- Family contacts - chosen as a feature with low implementation over-head to be included in an initial set of minimal functionality in support of goal 3.
- Shopping lists - chosen as a 'nice to have' feature which could be implemented for version 1 of the project given sufficient time, but which is also a discrete area of functionality which could be added later as per goal 3.
- Meal planning - also chosen as a 'nice to have' feature which could be added in a future version of the app, aligning with goal 3. This functionality would likely build on that of the shopping lists feature, and was therefore regarded as unlikely to be included in version 1.
- User feedback and information - required to support goal 2.
- Search and filter - required to support goal 2.

### Epics
Themes were then refined into the following epics:

- Account management
  - Account registration
  - Account sign-in
  - Account sign-out
  - Account deletion
  - User profile
- Calendar/event scheduling
  - Scheduling events
  - Event responses
  - Event deletion
  - Editing events
- Family contacts
  - Adding family contacts
  - Amending family contacts
  - Deleting family contacts
  - Viewing family contacts
- Shopping lists
  - Creating shopping lists
  - Amending shopping lists
  - Deleting shopping lists
- Meal planning
  - Creating a meal plan
  - Editing a meal plan
  - Deleting a meal plan
- User feedback/information
  - Notifications
  - User feedback
- Search and filter
  - Searching calendar events
  - Searching contact list
  - Searching shopping lists
  - Searching meal plans

### User stories
User stories required to implement each epic were created. These were categorised according to whether they were 'must have' features required to implement a Minimum Viable Product (MVP).
Please see the [Google sheet](https://docs.google.com/spreadsheets/d/11wcDHeqr85VaHXdJjATod_WECRY03IRUlGgT_L_ikIw/edit#gid=0) for detail.

## Agile development methodology
GitHub issues and projects were used to document and track an agile development approach.
A GitHub issue was created for each user story, with labels to indicate if they were required for the MVP. A GitHub milestone was created to represent the product backlog. All user stories were initially added to the product backlog.

Development work was scheduled using a series of iterations each with a timebox of three working days, representing a total 16 story points (although the duration of each iteration in calendar days was variable due to fitting the three working days around work and other commitments).

A GitHub project board was created for each iteration, and user stories moved from the product backlog into the relevant iteration as each cycle of work began. User stories were labelled as 'must have', 'could have' or 'should have' goals for that specific iteration, and assigned story point values.  Story points for 'must have' user stories never exceeded 9 (60%). Some iterations also contained 'tasks' for activity not represented as user stories, such as setup/configuration and design/styling.

A project kanban board was used to track progress, with user stories moved between 'Todo', 'In Progress' and 'Done' columns as appropriate. For example, the iteration 2 project board was captured at the start, in the middle and at the end:

<p align="center">
    <img src="readme_assets/iteration2_start_kanban.png" width=600>
    <img src="readme_assets/iteration2_mid_kanban.png" width=600>
    <img src="readme_assets/iteration2_end_kanban.png" width=600>
</p>

The project boards in their final form can be accessed at [TribeHub GitHub Project Boards](https://github.com/andy-guttridge/tribehub_react/projects?query=is%3Aopen).

Additionally, Notion was used to note and track other miscellanious tasks as they arose during development.

## Planning

### Mockups

Wireframes were produced based on those user stories that had been identified as required for the MVP.
These were based on a mobile view of the site, as TribeHub is very much a mobile first web app.

<p align="center">
    <img src="readme_assets/pp5_wireframes.png" width=600>
</p>
<p align="center">
    <a href="readme_assets/pp5_wireframes.pdf" target="_rel">Link to fullsize wireframes</a>
</p>
The wireframes were critical to the development of the site and were invaluable in terms of mapping and visualising the 'flow' through the site and the UI, however the final product varies from the wireframes in a number of respects, largely for technical and/or usablility reasons: 

### Data models
Data models were planned alongside the wireframes. These are documented in the read-me for the [TribeHub Django Rest Framework API](https://github.com/andy-guttridge/tribehub_drf).

## Design

### Colours
To incoporate a minimalistic appearance was the primary design aim for the site. This is in order to highlight the detailed information and content throughout the site.

The main color used is rgb() that represents a calm and thrustworthy color type, in order to make the user feel relaxed and comfortable.


A white background was chosen for the site's main theme, to maximise contrast and provide a clean, straighforward and uncluttered look.
Coolor red was chosen for its vibrancy - this is used as the site's 'primary' colour to indicate clickable UI items. The 'secondary' and 'accent' colours were then chosen to complement it, using the algorithms in Adobe Colour Wheel, and then darkening the colours to increase contrast against the background.

 chosen to stand out against the dark background while also being a 'restful' colour. The secondary and accent colours are two different shades of grey, chosen to be unobtrusive.





### Fonts
Google fonts were used for the project.
Fredoka One was chosen for the TribeHub logo `<h1>` element and `<h2>` headings used for the main page/section headings. The aim was to find a fun, friendly yet clear and legible font, and was selected after trying a number of possibilities suggested in this [shapegrams blog post on 'Fun Fonts for Every Season'](https://shapegrams.com/fonts/).

Nunito was chosen for `<h3>` and `<h4>` elements (used as sub-headings within major pages/sections) because it is similar to Fredoka One, but has a 'thinner' look better suited to smaller headings.

Lato was chosen as a font for all non-heading text elements, based on its popularity as a highly legible font for web text content (e.g. https://fontandswatch.com.au/fonts/lato-font/#:~:text=Lato%20Font%20comes%20in%2018,1%20billion%20audiences%20per%20day.)

## Features
### [](https://github.com/vivignutz/balcongardens-fe#navbar--search)NavBar & Search

- Contains the necessary links for navigation throughout the site.
- Updates links are based on user state.
- The searchbar makes it possible search among the various listings.
- When user is using a small screen, the NavBar toggle turns into a burger icon.

[![Navbar](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/menu_bar1.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/menu_bar1.png)

[![Navbar](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/menu_bar2.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/menu_bar2.png)

[![Navbar](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/menu_bar_col.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/menu_bar_col.png)

### [](https://github.com/vivignutz/balcongardens-fe#cars-list-page)Post List page

- Shows all the posts on the site offered by users.
- Provides the vital information about each post.

[![PostList](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/posts_page.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/posts_page.png)

### [](https://github.com/vivignutz/balcongardens-fe#car-detail-page)Post Detail page

- Contains detailed information about each post: difficulty leve, type of plant, etc.
- Includes links for the post owner to update or delete the post.

[![Post](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/post.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/post.png)

## [](https://github.com/vivignutz/balcongardens-fe#car-edit-page)Post Edit page

- Provides capability for the user to update an existing post.

[![EditPost](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/edit_post.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/edit_post.png)

## [](https://github.com/vivignutz/balcongardens-fe#profile-page)Profile page

- The profile page gives the user the possibility to get more followers, and be between the most followed users of the plattform.
- \*\*\*This page is still being developed, and in a near future new features like "Bio" and "City" will be provided to all users. These features already can be seen at the API.

[![ProfilePage](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/profile.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/profile.png)

[
![Profile small screens](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/profile_small.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/profile_small.png)

## [](https://github.com/vivignutz/balcongardens-fe#edit-profile)Edit Profile

- Edit profile makes it possible for the user to update their existing information.

[![Edit Profile](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/static/edit_prof.png)](https://github.com/vivignutz/balcongardens-fe/blob/main/src/assets/edit_prof.png)

## [](https://github.com/vivignutz/balcongardens-fe#feed-page)Feed page

- On the Feed page all posts offered will be listed in an infinite loading process, according to the followed profiles. This is so the users can have the experience to scroll the screen for more and more posts.

## [](https://github.com/vivignutz/balcongardens-fe#saved-page)Liked page

- Registered users have the possibility to see their liked posts by clicking on "Liked" at the menu bar. All posts that a user likes will appear on a list form.

### [](https://github.com/vivignutz/balcongardens-fe#future-features)Future Features

Some future features were idealized to be implemented:

- Set the "Bio" and "city" at Profile page, in order to give the users the possibility to know the user their are following.
- Offer more search options with filters based on different criteria.
- Implement a star rating system for the plants offered to rate the plant offerers in order to increase trust and credibility of the community.
- Implement a location algorithm to allow users to search for plants or offeres through a certain distance, connected with the "City" field.
- To offer the functionality for an image gallery to allow the offeres to upload more pictures of the plants to give.


### CRUD functionality
Gro features full Create, Read, Update and Delete functionality, via the UI implemented in React and the Django Rest Framework API.

- Create - users can register a new user account as a Gro administrator, and then create further user accounts for their Gro users. Gro administrators can create contacts, and all authenticated users
- Read - authenticated users can view their and other users profile image and display name. Gro administrators can also view a list of all their tribe members.
- Update - authenticated users can update their profile image, display name and password, and edit and save calendar events they have created. Additionally, tribe administrators can edit contacts and all calendar events for the tribe.
- Delete - authenticated users can delete calendar events they have created, and their user profiles. Tribe administrators can delete all calendar events, contacts, and user profiles. 

### Future improvements and features

#### Short term future improvements
The following fixes and improvements would be made in the short term as a high priority if more time were available:

- Full synchronisation of state between components - currently if a user responds to an event via the notifications menu, this is not reflected in the calendar events list until the calendar data is reloaded from the server. Likewise, the notifications menu does not automatically refresh if an event is edited or added. This is because the notifications menu and calendar hold their own state and are separated from each other in the 'component tree'. Another similar issue is that if a user updates their display name or profile picture, this is not reflected in the welcome message in the header or in calendar events until the user refreshes the page. These issues could be resolved by refactoring the app so that as much state as possible (e.g. calendar events, notifications etc as well as profile data ) is held by top level context objects and ensuring that all components dependent on such state update themselves when there is a change, or by using a state management library such as Redux.
- Automatically display any events for the current day - currently the user has to select a day on the calendar to see any events when the page first loads, even if there are events for the current day.
- Refactoring to reduce the number of requests to the REST API - when the user selects a new month on the calendar, the React frontend requests events for 12 months either side of the current month, in order to 'buffer' the data and prevent a delay in data being displayed if the user skips a few months forwards or backwards. While this provides a relatively seamless user experience, it also means more data than necessary is being fetched in the background. This could be reduced by only fetching a full two years worth of data when the `TribeHome` component first mounts, and subsequently only loading one additional month at the 'extreme end of the range' each time the user changes month. Additionally, the `MyTribe` and `EventDetailsForm` components both separately fetch details of the current user's tribe from the API independently. Implementing a top level context object to fetch this data when the app first loads and make it available to the whole component tree could further reduce the number of data fetches. 
- Password strength checking for all accounts - the custom Django Rest Framework code that enables tribe administrators to create additional user accounts for tribe members does not currently 'hook in' to Django's built-in checks for password strength.
- Reassign ownership of events created by deleted users - currently events are deleted if the user who created them deletes their account. This avoids any issues with 'orphaned' instances in the database, but a better solution would be to automatically or optionally transfer ownership of such events to the tribe administrator.
- Transfer of tribe admin status to another user - in the event a tribe administrator closes their account, all user accounts associated with the tribe are closed and data deleted. This is to prevent 'orphaned' tribes and tribe members with no administrator. A better solution would be to enable the transfer of tribe admin status to another user.
- All day calendar events.
- Improved event duration input - the current dropdown with a selection of pre-set duration values was chosen for speed of implementation. A more flexible means of selecting the durations would improve the user experience.
- A 'no reply' default event response status - currently each user can only have an 'accepted' or 'not accepted' status for each calendar event, with the default being 'not accepted'. This means that while users can actively accept an invitation, they cannot actively decline. This is acceptable for a first iteration of a minimum viable product, but a better user experience would be for the default status to be neutral, so that a user can either actively accept or decline.
- Improvements to 'single page mode' - the priority for the first iteration of TribeHub was to provide the best possible experience for mobile users, and while single page mode does take advantage of larger screen sizes, it is really still an expanded version of the mobile experience. A better tablet and desktop experience could be achieved by using a React library such as [Big Calendar](https://jquense.github.io/react-big-calendar/examples/?path=/story/about-big-calendar--page) to implement a larger 'outlook' style calendar where details of events are visible on the actual calendar itself. A modal or 'popover' type component would be implemented to present an additional layer of detail and to allow creation and editing of events.

#### Longer term future features
Lower priority, longer term features to be added are:

- Refactoring the events data format to adopt the iCal standard, as a first step towards implementing integration with external calendars such as Gmail etc.
- End dates/date ranges for repeat events (e.g. 'repeat weekly until 1 December 2023').
- Exceptions to repeat event rules (e.g. a user could set up an event to recur weekly every Wednesday, but could create an exception so that one recurrence is on a Thursday).
- Exceptions to 'accept/decline' responses for recurrences (e.g. the user could accept all recurrences and then decline them on an individual basis).
- Notifications to remind users of events ahead of time and push notifications.
- Day/week/year views for the calendar.
- Avatars for contacts.
- A 'banner image' for the whole tribe which can be set by the tribe admin. This would appear at the top of the page or as a background.
- Tribe colour themes which can be set by the tribe admin and/or colour themes which can be set by the user. This would be relatively straightforward to implement with TailwindCSS and daisyUI.
- Read/unread status for notifications - currently the notifications menu badge counts the number of notifications, and users can reduce the count only by deleting notifications. Flagging notifications as read or unread and giving the user the ability to mark each notification on an individual basis would be more in line with the behaviour of other apps/websites. 
- Optionally adjusting calendar event dates and times to reflect the user's local timezone.
- Shopping lists and items, integrated with the calendar system.
- Meal plans, intregrated into shopping lists.
- UI improvements, e.g. an avatar based UI for inviting tribe members to events, and 'popovers' or 'callouts' for displaying calendar events.

Additionally, a native iOS app implementing the existing features in Swift and UIKit is planned (the Django Rest Framework API has been set-up to allow CORS requests from multiple domains with this in mind).

## Frameworks, libraries and dependencies

### React-Calendar
- [react-calendar](https://github.com/wojtekmaj/react-calendar) - this React library was used to implement the calendar. This is critical to the user experience as the calendar is a fundamental feature of the app, and creating such a calendar 'from scratch' would have been impractical within the time allowed for the project. React-Calendar was chosen because it is relatively lightweight and straightforward to use, enabling the key features to be implemented quickly, because it is compact in terms of its style, making it suitable for use on small mobile screens, and because it provides flexibility with respect to customisable CSS and calendar cell content (e.g. to enable the 'dots' used to indicate when there are events on a given day).

### React-Router-DOM
- [react-router-dom](https://www.npmjs.com/package/react-router-dom) - this library enables 'client side routing' for React web applications, and is used to implement basic routing in TribeHub, i.e. to implement the links on the bottom navbar, and register, sign-in and sign-out links. Using React-Router-DOM also enabled implementation of 'single page mode'to enhance the experience for users on larger screens. The `useSinglePage` custom hook is referenced in `App.js`, with different `Route` components conditionally rendered for the various paths depending on whether the app is running in single page mode. The `useLocation` hook from React-Router-DOM is used in some components to determine the current URL and respond accordingly, for example by ensuring the correct nav button is highlighted in the bottom navbar for mobile users.

### ReactDOM
- [react-dom](https://reactjs.org/docs/react-dom.html) - react-dom is used to manipulate the DOM outside of a specific component, and supports the user experience by enabling modal dialogs to be appended to the top level of the DOM (important for accessability) and alerts to be appended to specific components. For example, notifications are fetched by the NotificationsMenu component, but this takes the form of a dropdown menu, so using ReactDOM allows the component to 'reach out' into the DOM and display error alerts in a more obvious location than inside the dropdown.

### Axios
- [Axios](https://www.npmjs.com/package/axios) - the axios library was chosen to simplify making HTTP requests to the REST API (e.g. not having to manually configure HTTP headers), and because it enables simple implementation of 'interceptors' which are used to request a refresh token in the event of a HTTP 401 error. This enhances the user experience beacuse an authenticated user remains signed in for up to 24 hours, rather than having to sign in again after five minutes.

### JWT Decode
- [jwt-decode](https://www.npmjs.com/package/jwt-decode) - used to decode Base64URL encoded JSON web tokens.

### Tailwind CSS
- [TailwindCSS](https://tailwindcss.com/) - TailwindCSS was chosen partly in order to gain experience with an alternative to Bootstrap, and for its flexibility and quality of documentation. 

### daisyUI
- [daisyUI](https://daisyui.com/) - this CSS component library is a TailwindCSS plugin, specifically chosen because of the 'bottom navigation' component which allowed quick implementation of a mobile-app style navbar at the bottom of the screen to provide a high quality mobile first user experience, and it's simple customisable colour theme functionality which enables a website to be built with a small number of colours represented by semantic CSS classes. This was well suited to TribeHub, which only requires a small number of colours with an emphasis on easy identification of UI elements. DaisyUI also supports specific dark mode themes, and although not a primary reason for choosing this library, the feature was utilised for an additional 'quick win' in terms of user experience.

### React Bootstrap Icons
- [React Bootstrap Icons](https://www.npmjs.com/package/react-bootstrap-icons) - this icon library was selected for the high quality and simplicity of the icons, and easy integration with React.

## React features used to enhance user experience
### Custom hooks
The `useSingle` page custom hook is used throughout the app so that components can check whether the app is currently running in 'single page' mode, and render themselves accordingly, for example by applying appropriate CSS classes for the 'mobile' versus 'single page' views. Many components are reliant on a `useCurrentUser` hook to determine whether the current user is authenticated, and to obtain various details about the user such as profile image, display name and whether they have tribe admin status. 

## Testing

### Manual testing
Manual tests were devised for each user story to be implemented for the project. 
These were performed on the final, deployed version of the site and are documented on the [TribeHub user stories spreadsheet](https://docs.google.com/spreadsheets/d/11wcDHeqr85VaHXdJjATod_WECRY03IRUlGgT_L_ikIw/edit#gid=0).

Several tests failed on the first attempt. In these cases, details of how the issues were addressed and the outcome of further testing are provided. All tests were passed after issues were resolved.

In addition, the site was deployed early and subject to continual user testing throughout the development process. This resulted in a number of enhancements to the user experience, which are documented in the user stories and planning sections above.

### Automated tests
Four automated tests were written for the `Header.js` component. These are in `src/components/__tests__/Header.test.js`.

The tests are as follows, and all passed:

- Test that the Header component renders with the logo text, and without a sign-out button when the user is not authenticated.
- Test that the Header renders a welcome message with the user's name when authenticated.
- Test that the Header renders a sign-out button for an authenticated user.
- Test that the Header does not render a welcome message or sign-out button after an authenticated user has pressed the sign-out button.

### Validator testing

### W3C CSS validator
All CSS files were passed through the W3C validator. The following errors and warnings were flagged:

- The TailwindCSS `@apply` directive was identified as a 'CSS hack' and in some cases as a 'parse error'. `@apply` is a directive provided by TailwindCSS that allows multiple utility classes to be applied to a single CSS class. This is particularly useful when working with existing libraries and components that do not themselves use Tailwind, and was essential for integrating `react-calendar` with Tailwind. It was also used to globally apply styles to specific HTML elements, for example Google Fonts are defined as Tailwind classes in `tailwind.config.js` and these classes are then applied globally to elements such as headings, paragraphs etc in `index.css`.

    These warnings and errors relating to `@apply` were flagged in `Calendar.module.css`, `Landing.module.css`, `TribeHome.css`. They were ignored as this is a valid TailwindCSS directive which generates valid CSS for the browser and is required to correctly style some components in TribeHub. Additionally, the TailwindCSS linter for VSCode flagged no errors for these.

- The `:global` selector which can be used in CSS modules to apply styles globally is not parsed by the W3C validator. This is used extensively in the `Calendar.module.css` file to override the default CSS classes defined in the library with Tailwind/daisyUI classes. 

    These validator errors were ignored as `global:` is identified as valid syntax in the [CSS modules documentation](https://github.com/css-modules/css-modules) and is required to correctly apply CSS styles to the calendar.

- The `@tailwind` and `@layer` rules provided by TailwindCSS and used in the `index.css` file were flagged as errors. These were ignored as they are valid Tailwind syntax and not flagged as errors by the Tailwind linter.

- An invalid value of `scaleY(100%)` was used for the `transform` property in `ContactDetailsForm.module.css`, `ContactSearch.module.css`, `EventDetailsForm.module.css`, `EventSearch.module.css` and `TribeMemberDetailsForm.module.css`. This was corrected to `scaleY(1)` in each case.

- A warning that `skewY()` is a vendor extension was flagged in `Landing.css`. The MDN web docs reference for this CSS function identifies high browser compatibility, so this warning was ignored.
<p align="center">
    <img src="readme_assets/skewy.png" width=500>
</p>

- Warnings about `-apple-system`, `-webkit-font-smoothing` and `-moz-osx-font-smoothing` vendor extensions were flagged in `index.css`. These were ignored as they are generated by the TailwindCSS installation and necessary for the library.

### ESLint JavaScript validator

All JavaScript files were validated using the ESLint JavaScript validator.
The following issues were identified and corrected:

- Unnecessary semi-colons at the end of some statements.
- Unescaped apostrophies in HTML text in some components.
- An unused variable.
- Missing React import statements.

### WAVE web accessability testing

Testing with the WAVE validation revealed the following issues:

- Contrast issues with buttons. The text colour for buttons in the primary and secondary colour was lightened, while outline buttons were changed from primary to a dark (or light for dark mode) colour, and the font size was increased for all buttons. This successfully resolved the issues.

- Contrast issues were also detected between the dots on the calendar indicating where there are events for a given day. This was more difficult to address, because the calendar cells can have a number of different colours depending on their current state. After some experimentation, the `mix-blend-mode` attribute with a value of `difference` was used on these elements to invert their colour against that of the background. This means the colour of these indicators might not fit as well with the colour scheme of the site, but it eliminates the contrast issues.

- Three further contrast errors were found, but these were ignored as they apply to hidden elements which provide additional information for screen readers.

- Avatar images throughout the website had the same text for the alt attribute. This was addressed by passing a `displayName` prop through to the Avatar component, and using this to generate an appropriate alt text value for each user.

- Several form elements with no label were flagged on the profile update form and the event search form (caused by missing or incorrect id attributes on input elements), and one element with a duplicate id on the contacts form (caused by a naming clash with another element on the add event form).

- The label containing the notifications indicator was found to contain no text. This was rectified by putting a `<span>` element with the Tailwind CSS `sr-only` class inside the label, providing a read out of the number of notifications present for screen readers but visually hidden. This label was also flagged as orphaned from its form control by the Wave validator, however this was not fixed, as the label is used instead of a button for the DaisyUI dropdown component in order to overcome a bug in Safari.

- Missing labels were found for the input elements which are part of the DaisyUI collapse components used to reveal further detail for each calendar event. This was rectified by passing the unique key value generated for each CalEvent instance as a `calEventId` prop, using this to generate a unique id for each input and associating a screen reader only label to each one.

- The Wave report contained an alert about the `noscript` element. This was to flag that content within this element must be accessible. Since the element contains a simple text reminder that JavaScript must be enabled to use the website, this was deemed not to be an issue.

- Skipped heading levels in the notification items menu and on calendar events were identified. The former was addressed by changing the `h3` elements used in the `NotificationItem` component to `h2` and styling to look like `h3`. The headings for event titles on calendar events were changed from `h4` to `h3`, which would appear to be correct as the next heading above them is an `h2`, however this did not resolve the validator error. `h2` and `h1` were also tested for these headings, but this still did not resolve the error. These elements were then changed to `p` and the error was resolved. The `h5` headings within the 'details' collapse component at the bottom of calendar events were also changed to `p` elements to resolve similar errors.

- Category icons on calendar events did not have unique text for the `alt` attribute. This was due to a bug rather than an oversight, and was corrected. Wave then flagged a 'redundant alternative text' alert, meaning that another nearby element had an image with the same `alt` text. This is because more than one event in the list of events had the 'shopping' category - given the purpose and meaning of the icon, a repeat occurence of the alt text is correct and was deemed not to be an issue.

### Lighthouse testing

Lighthouse testing was undertaken in incognito mode for every URL for mobile and in single page mode, in both light and dark modes, and on the landing page, sign-in page and registration page. Each page/section was tested with add, edit and search forms and modal dialogs open.

WAVE validation had already been completed and most accessability issues fixed, however lighthouse did reveal that button elements did not have id attributes, which are required by assistive technologies. 

After this issue had been addressed, every page achieved 100% for accessability.
All pages achieved 100% for best practices, except for the landing, registration and sign-in pages, where HTTP 401 errors in the console reduced the score to 92%. This is expected as a consequence of a non-authenticated user being redirected away from content requiring authorisation.

Performance scores were not as high, ranging from a low of 61% for the contacts page with the search form being opened on mobile to 90% for the app in single page mode with the add tribe member form being opened. Performance scores for the majority of pages/scenarios ranged from the low 70s to high 80s. The same potential performance improvements were identified in each case:

- Serve images in next gen formats.
- Reduce unused JavaScript.
- Eliminate render-blocking resources (e.g. deliver critical JavaScript and CSS inline).
- Minify JavaScript.
- Efficiently encode images.
- Preload larges contentful paint image.
- Serve static assets with efficient cache policy.
- Avoid chaining critical requests.
- Use user timing marks and measures.
- Keep request counts low and transfer sizes small.
- Avoid large layout shifts.
- Avoid long main-thread tasks.

The hero image on the landing page was compressed in order to improve loading time. The other potential improvements could be implemented in a future iteration.

<p align="left">
    <span>Lowest lighthouse score: contacts page with search form open, mobile: </span>
    <br />
    <img src="readme_assets/lighthouse_mobile_search_contact.png" height=100>
</p>
<p align="left">
    <span>Typical lighthouse score: tribe home page with add events form open, mobile: </span>
    <br />
    <img src="readme_assets/lighthouse_mobile_tribe_home_add_events.png" height=100>
</p>
<p align="left">
    <span>Highest lighthouse score: single page mode with add tribe member form open, desktop: </span>
    <br />
    <img src="readme_assets/lighthouse_single_page_desktop_add_tribe_member.png" height=100>
</p>

### Resolved bugs
- During implementation of the `NotificationItem` component, requests to the REST API for the data for the events with which each notification is associated were frequently resulting in an HTTP 500 internal server error. A version of the API running on a development server was used for debugging. This revealed that the number of simultaneous requests for data coming from a large number of NotificationItems was overwhelming the free tier ElephantSQL database server. The fix was to add the full data for each event to the notification JSON served by the API, which meant that only one network request was required to fetch the notification and event data together. 
- During testing, a large amount of empty space was noted at the bottom of each page, but only for some user accounts. No elements causing this could be identified using the Chrome developer tools, and elements were manually removed from each component until the culprit was found. This revealed that the unordered list of notifications inside the DaisyUI dropdown component used for the notifications menu was taking up vertical space in the document even when closed/not visible. This was only noticeable for users with a large number of notifications and hence a very long list inside the menu. The issue was addressed by applying the Tailwind CSS hidden class to the unordered list when not visible. An event listener was added to detect clicks outside of the menu and close the list accordingly.
- After search functionality had been added, it became apparent that edits to events and event deletions made from events in the search results were not reflected in the calendar. This was fixed by passing `childDidSaveEvent` and `setChildDidSaveEvent` props down through the component tree to `EventSearch.js` component, through to the `CalEvent.js` component  and on to the `EventDetailsForm.js` component, to trigger the calendar to reload it's data after a change has been made. This was a 'quick fix' to correct the bug, and would be a candidate for refactoring in future.

### Unresolved bugs
- Users accessing TribeHub from iOS devices, Safari on MacOS, Samsung Internet on Samsung devices and possibly others must turn off 'Prevent Cross Site Tracking' (Apple devices), 'Smart Anti-Tracking' (Samsung devices) or other similar features in order to use the web app. This is because the Django Rest Framework API and the React front-end are hosted on separate domains using Heroku, and cross-domain requests from the front-end to the API are blocked by these anti-tracking features. It appears there is no solution to this, other than to host the API and front-end on the same domain (reference - https://stackoverflow.com/questions/56972162/is-there-a-workaround-for-safari-ios-prevent-cross-site-tracking-option-when).

## Deployment
To deploy to Heroku, follow these steps:

- Fork or clone this repository in GitHub.
- If you have also cloned and deployed your own version of the TribeHub Django Rest Framework API, you will need to ensure the value of `axios.defaults.baseURL` in `src/api/axiosDefaults.js` is set to the base URL for your API. Pull to your local development environment and push back to GitHub if necessary; otherwise, leave as is to use the original TribeHub API.
- Log in to Heroku.
- Select 'Create new app' from the 'New' menu at the top right.
- Enter a name for the app and select the appropriate region.
- Select 'Create app'.
- Select the 'Deploy' tab at the top.
- Select 'GitHub' from the deployment method options to confirm you wish to deploy using GitHub. You may be asked to enter your GitHub password.
- Find the 'Connect to GitHub' section and use the search box to locate your repo.
- Select 'Connect' when found.
- Optionally choose the main branch under 'Automatic Deploys' and select 'Enable Automatic Deploys' if you wish your deployed site to be automatically redeployed every time you push changes to GitHub.
- Find the 'Manual Deploy' section, choose 'main' as the branch to deploy and select 'Deploy Branch'.

When deployment is complete, you will be given a link to the deployed site.

## Credits

### Code
- How to use the React Router `<BrowserRouter>` component to provide history context to `<Router>` components is from [this Stack Overflow article](https://stackoverflow.com/questions/65425884/react-router-v6-error-useroutes-may-be-used-only-in-the-context-of-a-route)
- The technique to use an event handler to store the current size of the window in state variables in order to conditionally render components was adapted from [this Stack Overflow question](https://stackoverflow.com/questions/62954765/how-to-do-conditional-rendering-according-to-screen-width-in-react)
- Code to handle current user context in `src/contexts/CurrentUserContext.js` was adapted from Code Institute 'Moments' React walkthrough lessons
- Code to create and use axios interceptors to refresh tokens in `src/contexts/CurrentUserContext.js` and `src/utils/utils.js` was adapted from the Code Institute 'Moments' React walkthrough lessons
- The technique to add modal dialogs to the end of the body element in the DOM is from [upmostly.com](https://upmostly.com/tutorials/modal-components-react-custom-hooks)
- How to use the `:global` selector in CSS to ensure styles are overriden in a React component is from [Stack Overflow](https://stackoverflow.com/questions/42191671/css-modules-reactjs-parent-and-child-css-classes-in-different-components)
- How to use `require` to ensure webpack processes local images is from [Stack Overflow](https://stackoverflow.com/questions/34582405/react-wont-load-local-images)
- How to use CSS filters to colour a SVG is from [Stack Overflow](https://stackoverflow.com/questions/22252472/how-can-i-change-the-color-of-an-svg-element)
- How to define a CSS class as part of a DaisyUI theme is from [GitHub](https://github.com/saadeghi/daisyui/discussions/640)
- How to iterate over the keys of a JavaScript object in React is from [Stack Overflow](https://stackoverflow.com/questions/40803828/how-can-i-map-through-an-object-in-reactjs)
- The technique for handling multiple selection elements in controlled React forms is from [Stack Overflow](https://stackoverflow.com/questions/50090335/how-handle-multiple-select-form-in-reactjs)
- How to correctly use the useCallback hook to declare a function outside of useEffect and call from inside useEffect to enable code reuse is from [Stack Overflow](https://stackoverflow.com/questions/56410369/can-i-call-separate-function-in-useeffect)
- How to add a number of minutes to a DateTime object is from [StackOverflow](https://stackoverflow.com/questions/1197928/how-to-add-30-minutes-to-a-javascript-date-object)
- The technique for using a timer to prevent excessive network requests when the values of input elements on a search form change is from the Code Institute Moments walkthrough project
- How to redirect to an appropriate page when the user enters an invalid URL using the Navigate component from React-Router-DOM has been adapted from [copycat.dev](https://www.copycat.dev/blog/react-router-redirect/)
- How to use Google Fonts in a Tailwind CSS project is from [daily-dev-tips.com](https://daily-dev-tips.com/posts/using-google-fonts-in-a-tailwind-project/)
- How to invert the colour of an element compared to its background is from [Stack Overflow](https://stackoverflow.com/questions/17741629/how-can-i-invert-color-using-css)
- How to create divs with diagonal lines is from [9elements.com](https://9elements.com/blog/pure-css-diagonal-layouts/)
- How to use the text-shadow CSS attribute to add an outline to text is from [Stack Overflow](https://stackoverflow.com/questions/57464935/font-outline-using-only-css)
- How to configure JEST to allow tests with Axios v1 and above is from [Stack Overflow](https://stackoverflow.com/questions/74940474/jest-encountered-an-unexpected-token)

The following documentation was referenced extensively throughout the project:

- [React documentation](https://react.dev/reference/react)
- [React Router Documentation](https://v5.reactrouter.com/)
- [TailwindCSS documentation](https://tailwindcss.com/docs/)
- [DaisyUI documentation](https://daisyui.com/components/)

### Media
- Placeholder screenshots image used on the wireframes by u_fg0tkeqgiy on [Pixabay](https://pixabay.com/vectors/view-web-secure-image-ipad-laptop-7321141/).
- Hero image used on the landing page by Pexels on [Pixabay](https://pixabay.com/photos/child-couple-daylight-family-1844901/).
- Placeholder avatar image used on the wireframes and in the app by Stephanie Edwards on [Pixabay](https://pixabay.com/vectors/blank-profile-picture-mystery-man-973460/).
- Fidget spinner image used for loading spinner by b0red on [Pixabay](https://pixabay.com/vectors/fidget-spinner-add-a-d-spin-2304681/)
- Images used for event category icons:
  - Club icon used for club by Clker-Free-Vector-Images on [Pixabay](https://pixabay.com/vectors/clubs-cards-club-shape-card-games-33561/)
  - Mortar board icon used for education Clker-Free-Vector-Images on [Pixabay](https://pixabay.com/vectors/graduation-cap-graduation-education-311979/)
  - Medical bag icon used for medical by OpenClipart-Vectors on [Pixabay](https://pixabay.com/vectors/red-cross-aide-assistance-158454/)
  - Musical note icon used for music by ruhbastard on [Pixabay](https://pixabay.com/vectors/music-note-music-note-musical-notes-1967480/)
  - Metallic O icon used for other by Clker-Free-Vector-Images on [Pixabay](https://pixabay.com/vectors/english-alphabets-o-letters-15th-33793/)
  - Shopping trolley icon used for shopping by Clker-Free-Vector-Images on [Pixabay](https://pixabay.com/vectors/shopping-cart-caddy-shopping-trolley-304843/)
  - Volley ball icon used for sport by Clker-Free-Vector-Images on [Pixabay](https://pixabay.com/vectors/volleyball-sport-black-white-306791/)
  - Aeroplane icon used for vacation by GDj on [Pixabay](https://pixabay.com/vectors/jumbo-jet-airplane-aeroplane-1801305/)
  - Office desk icon used for work by OpenClipart-Vectors on [Pixabay](https://pixabay.com/vectors/computer-office-worker-typing-146329/)
  - Present icon used for celebration by chachaoriginal on [Pixabay](https://pixabay.com/vectors/red-icon-present-gift-wrapped-1902863/)
  - Car icon used for outing by Clker-Free-Vector-Images on [Pixabay](https://pixabay.com/vectors/car-automobile-sedan-four-door-car-35502/)
  - Cat icon used for pets by Lohrelei on  [Pixabay](https://pixabay.com/vectors/cat-kitten-sitting-silhouette-1144200/)
- Fonts:
    - [Google Fonts Fredoka One](https://fonts.google.com/?query=fredoka+one&sort=popularity)
    - [Google Fonts Nunito](https://fonts.google.com/specimen/Nunito?query=nunito&sort=popularity)
    - [Google Fonts Lato](https://fonts.google.com/?query=lato&sort=popularity)