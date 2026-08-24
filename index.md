#CS 499 Computer Science Capstone ePortfolio

Content:
Professional Self-Assessment
Code Review
Enhancement One: Software Design and Engineering 

Original: [index.tsx](ePortfolio/enhancement-one/original/index.tsx)

Enhanced: [index.tsx](ePortfolio/enhancement-one/enhanced/index.tsx) · [MacroStat.tsx](ePortfolio/enhancement-one/enhanced/MacroStat.tsx) · [XPBar.tsx](ePortfolio/enhancement-one/enhanced/XPBar.tsx) · [MacroContext.tsx](ePortfolio/enhancement-one/enhanced/MacroContext.tsx) · [character.tsx](ePortfolio/enhancement-one/enhanced/character.tsx) · [_layout.tsx](ePortfolio/enhancement-one/enhanced/_layout.tsx)

Enhancement Two: Algorithms and Data Structures

Original: [macro_logger.py](ePortfolio/enhancement-two/original/macro_logger.py) · [character.py](ePortfolio/enhancement-two/original/character.py)

Enhanced: [progressionEngine.ts](ePortfolio/enhancement-two/enhanced/progressionEngine.ts) · [progressionRules.ts](ePortfolio/enhancement-two/enhanced/progressionRules.ts) · [progressionTypes.ts](ePortfolio/enhancement-two/enhanced/progressionTypes.ts) · [Character.ts](ePortfolio/enhancement-two/enhanced/Character.ts) · [CharacterContext.tsx](ePortfolio/enhancement-two/enhanced/CharacterContext.tsx) · [macroTypes.ts](ePortfolio/enhancement-two/enhanced/macroTypes.ts)

Enhancement Three: Databases

Original: [macro_db.py](ePortfolio/enhancement-three/original/macro_db.py)

Enhanced: [db.ts](ePortfolio/enhancement-three/enhanced/db.ts) · [validation.ts](ePortfolio/enhancement-three/enhanced/validation.ts) · [CharacterContext.tsx](ePortfolio/enhancement-three/enhanced/CharacterContext.tsx) · [macroTypes.ts](ePortfolio/enhancement-three/enhanced/macroTypes.ts)

Professional Self-Assessment:





Code Review URL
https://youtu.be/l7Qx68OSE4A 



Enhancement One:


Enhancement Two:



Enhancement Three:



Narrative One:
[Milestone 2 Narrative (2).docx](https://github.com/user-attachments/files/31359775/Milestone.2.Narrative.2.docx)
1.	Briefly describe the artifact. What is it? When was it created?
The artifact I selected for this enhancement is the home screen and navigation structure of MacroTrackerRPG app. This is a React Native app I began developing in early 2026. MacroTrackerRPG approaches macro tracking as an RPG with a character progression system tied to logging your macros. This approach is aimed at users who struggle to stay consistent in tracking their macros and nutrition goals. By turning macro tracking into a game, it incentivizes consistency. 
2.	Justify the inclusion of the artifact in your ePortfolio. Why did you select this item? What specific components of the artifact showcase your skills and abilities in software development? How was the artifact improved?
I chose this artifact because it is a personal project that I am actively developing rather than a completed course assignment. I believe this fits perfectly into my ePortfolio because it shows real work that I’m doing outside of my courses. The components that best showcase my abilities in software development are the MacroStat, XPBar components, and MacroContext React Context layer. Originally, the Home screen contained repetitive blocks of code for each of the macro categories. I extracted these blocks into a reusable MacroStat component that can live on both the Home and Character screen which made it easier to implement gesture handling into the macro labels that now come from this component. I used a similar reusable component for the XP bar that now lives on both the Character and Home screen. I also replaced fixed pixel positioning with percentages which improves the responsiveness across different devices. The most significant improvement is replacing the hardcoded values on each screen with React Context that provides both the Home and Character screens with the same data. Before adding the Context layer, I built the Character screen in order to share data between it and the Home screen, because having React Context with only one screen would make it functionally no different from the separate hardcoded values on each screen. 
3.	Did you meet the course outcomes you planned to meet with this enhancement in Module One? Do you have any updates to your outcome-coverage plans?
I met the original course outcome I had selected, outcome four by improving the application architecture using recommended techniques and accomplishing industry-specific goals. By replacing repetitive blocks of code with reusable components and implementing state management with React Context, I made MacroTrackerRPG much easier to maintain and more aligned with industry standards. I also made progress in meeting outcome three with this enhancement by managing design trade-offs like choosing to use React Context rather than a state management library like Redux because it was not needed for this app's scale. Based on the feedback I received, I have updated my outcome-coverage plan. I am making progress towards outcome two by providing professional-quality documentation with the code review, narratives, and the ePortfolio. I will continue making progress towards outcome three by refactoring my XP algorithm and converting Python files to TypeScript in my next enhancement. I will address outcome five with the database enhancement where I will use input validation, parameterized queries, and Defense in Depth. Finally, I will address outcome one with the completion of the ePortfolio and the professional self-assessment where I will explain and document design decisions. 
4. Reflect on the process of enhancing and modifying the artifact. What did you learn as you were creating it and improving it? What challenges did you face?
While working on my enhancement, I learned that certain issues or bugs require restructuring rather than adding or editing code. While I was adding tap, hold, and drag gestures to the MacroStat component I originally had all three gestures modifying the same state to control whether expanded values were shown. This caused one gesture to overwrite the last and led to the state being broken and buggy. I attempted to debug this issue and continued trying several solutions, with each breaking something else. I then realized that the solution that was best suited for this issue was to give each gesture its own state to manage and update. One of the biggest challenges I faced was understanding how animation and rendering run on separate threads and that I would have to schedule an update on the JavaScript thread rather than directly updating the React State with the gesture handlers. I also struggled with setting up the React Context layer and had to learn the proper structure including using a hook to prevent direct access.
<img width="468" height="643" alt="image" src="https://github.com/user-attachments/assets/fa487ba5-35fe-4011-a331-5c0c46a48ead" />




Narrative Two:
[Milestone Three Narrative (3).docx](https://github.com/user-attachments/files/31359796/Milestone.Three.Narrative.3.docx)
1.	Briefly describe the artifact. What is it? When was it created?

The artifact I chose for this enhancement is the XP and Character class Python files for MacroTrackerRPG. The XP engine calculates XP based on the user’s day of macros against their pre-set target macros. The character class is what holds the state including XP and level. I created these Python files in early 2026 as prototypes before I began building the actual app. 

2.	Justify the inclusion of the artifact in your ePortfolio. Why did you select this item? What specific components of the artifact showcase your skills and abilities in algorithms and data structure? How was the artifact improved?

I chose this artifact because it demonstrates my ability to use algorithmic thinking to develop application logic. The component that showcases my skills in algorithms and data structures is the XP engine. In this artifact, I designed an algorithm that calculates XP by taking a user’s daily macros and evaluating them against their target. There is then a series of weights, thresholds, and penalties applied to the ratio between the day’s total and target to determine how much XP the user collects for the day. The artifact has been ported to TypeScript and the algorithm has been refactored to extract the hard-coded pre-set values for the weights and thresholds and store them separately in the progressionRules configuration file. Additionally, the algorithm runs in O(n) time complexity and O(n) space complexity by running over a config list of the macro categories with no nested loops. This improves the original design by combining separate individual blocks of code for each macro category into one single block that iterates over the list to evaluate each macro category. This change makes it much easier to edit or expand the macro categories list because it only requires changing the config rather than editing the engine or calculation logic.

3.	Did you meet the course outcomes you planned to meet with this enhancement in Module One? Do you have any updates to your outcome-coverage plans?

I met the course outcome that I had originally planned for this enhancement which is outcome three. I designed and improved the XP algorithm using algorithmic principles and analyzed the time and space complexity to confirm that the loop iterations run O(n). The list of macros is small and fixed and as a result will not demand much processing power on mobile devices. I also met outcome four during this enhancement by separating the app into layers that each handle a separate functionality. The app is separated into a nutrition, character, and progression layer that each handles its own responsibility without interfering with the other. I also restructured the Character class so that it returns a new character instead of modifying itself every time its stats are updated. This is important as it allows for React to detect the updated values because of the new instance whereas it would not detect the updates if the character instance were just modified. I am continuing making progress towards outcome two by providing professional quality documentation in this narrative and in the comments throughout my code that explain my design decisions. I still plan to address outcome five in the database enhancement with Defense in Depth through input validation and parameterized queries. Finally outcome one will be met with the completion of my ePortfolio and professional self assessment. 

4.	Reflect on the process of enhancing and modifying the artifact. What did you learn as you were creating it and improving it? What challenges did you face?

As I was modifying this artifact, I learned that even though my program logic may be sound and correct in one instance, it can still not work well when used in a different environment. In the original Python file for my character object, the character updated its XP directly in the same file and although this worked for my Python prototype, it does not work for the React Native app. React is not able to detect the change when the character itself is updated because it can only detect when it is given a different object. As a result, each time the character's XP or level is updated, it must return a new Character instead of modifying the existing one. 
<img width="468" height="656" alt="image" src="https://github.com/user-attachments/assets/67aedeb9-857e-4c98-8b39-ec99295b7c28" />


Narrative Three:
