# 
**Documentation for PictureIt**


# Introduction & Goals

<div  class="formalpara-title">

**Requirements Overview**

</div>

- Posting & Viewing high quality images
- Customizable filters & Advanced editing tools with Pixlr integration 
- Commenting, Liking, Saving posts, Hashtags 
- User generated Challenges & Competitions 
- Free (limited) & Subscription based versions



<div  class="formalpara-title">

**Stakeholders**

</div>

| Role/name    | Expectations |
| -------- | ------- |
| User (18-25 yo)  | View, share and interact with posts and other users   |
|Content Creator|Upload, edit photos to the app. Build a following|
|Advertisers|Advertise their product to a wide audience|
|Client|Have a successful and functional app with many user & creators|
|Investors|Platform growth. Return on investment|



<div  class="formalpara-title">

**Quality Goals**

</div>

| Priority | Quality| Motivation | 
| -------- | ------- |-------|
|1|Meets Security and Privacy regulations|Keeping user’s data safe|
|2|IOS & Android availability|Largest possible target audience|
|3|No downtime - 24/7 availability|Enhance user experience.|




# Solutions, Decisions and Risks

<div  class="formalpara-title">

**Solutions Strategy**

</div>

|Goal/Requirement|Architectural Approach|
|----------------|----------------------|
|Image Sharing/Posting|Microservice|
|Image editing / filters / third party integration of pixlr|Microservice|
|Discovery algorithm (hashtags, likes, comments)|Microservice|




<div  class="formalpara-title">

**Architecture Decisions**

</div>

|Problem|Considered Alternatives|Decision|
|---|---|---|
|Users want to post pictures in real time (1-2 seconds)|SOA: adaptive and flexible. Simpler implementation.|Microservices: SOA has issues with a sudden surge of users, we need a reliable and quick solution|
|Users want to see relevant posts|SOA: Algorithm can be updated and change without affecting the correct functioning of other services.|Microservices: Algorithm needs to quickly and dynamically adjust to user preferences through interactions (likes, comments, etc.)|
|User wants to see before & after versions of edited pictures|SOA: Saves images to database and exchanges requested data with user interface and third party services|Microservices: SOA would require many interactions with the database and be unresponsive|



<div class="formalpara-title">

**Risks and Technical Debt**

</div>

|Risk/Technical Debt|Description|
|---|---|
|Development costs|Microservices require a large team of developers to maintain, update and build the system|
|Data consistency|Microservices need to handle data independently which can lead to inconsistencies|
|Documentation|Each service requires its documentation, which can be a lot of work to update and maintain|



