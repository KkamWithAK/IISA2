# 01_SPEC.md: use case and system path

Use this file for the use case from your Week 2 storyboard. Keep the notes short enough to use while you work.

## User goal
<What is the person trying to achieve?>
The user is in a social VR setting, They are attempting to use the facial recognition system to enchance their VR conversations

## System inputs
<What does the person provide, and what data or context does the system receive?>
The user provides facial expressions (as part of natural speech) which is deteted by the system.

## Processing and technology
<What does the system extract, look up, classify, generate or decide? Which model, tool, data source or software component would carry out each important step?>
The system tries to map the change in the user's facial expressions and map it onto a VR Avatar. With facial detection software which can recieve data from cameras or physical trackers on the face.

## Intended result and next action
<What does the system return, and what can the person do next?>
If working as intended, The System is able to map the user's facial expressions onto their avatar in real time. Additionally, the user can see a viewport of their avatar in the corner of their screen.

## Fallback strategy
<What happens if information is missing, ambiguous, outside the system's scope or unavailable?>
If the system isn't fully confident, it will attempt to guess the mapping from the user to the avatar. In cases like this, the user can simply remake their face/continue normally

In other cases where the system has little to no confidence of the appropriate mapping, It deafults the avatar to a nuetral facial expression, and the user can use their controller to manually pick from a predefined set of facial expressions (happy, sad, angry, ...) and continue from there

## System path or interaction diagram
Add a flowchart, use-case diagram or system architecture sketch showing the person, input, processing, data or model or tool, response and next action. Label anything that is implemented, simulated or still planned.


## Test A: standard input
Input: The user is smiling then transitions to a frown

What the system receives: a live feed of the user's face through a camera

What it does: tracks points on the user's face and maps their translation onto their virtual avatar

Response and next action: The virtual avatar transistions it's smile to a frown just like the user. The user see's the viewport is exactly as they like, ao they continue their conversation like normal.


## Test B: problem input
Input: The user smiles while speaking, but their mouth is partially obscured. 

What the system receives: Incomplete or noisy facial-tracking data. The tracking software detects some facial featueres but cannot reliably determine the intended expression.

What it does: The system calculates low confidence due to the malformed input.The system attempts to guess the expression mapping.  It may incorrectly interpret the user's smile for a frown. 

Response and next action:
The avatar displays an incorrect expression (a frown). The user can see the incorrect facial feature in the viewport, and my retry to smile, or controll their avatar with the controller

## Review and revision
Use the tests to identify an interaction or system problem. Note the evidence, then describe one interaction change and one technology or system change. Explain why the changes help and run Test B again.

interaction problem, when the system goes wrong, there's only indication through the visual channel. As the user is in convresation with another digital avatar, it is likey that the visual channel is too occupied, same with the audiotry channel. hence, potentially using haptics as a way to request the user's attention and thus input is a way to go forwards.

## Test B: problem input (rerun)

Input: The user smiles while speaking, but their mouth is partially obscured.

What the system receives: Incomplete facial-tracking data, resulting in low confidence.

What it does: The system rejects the unreliable expression mapping and triggers a short haptic vibration through the user's controller. The avatar temporarily retains its last reliable expression.

Response and next action: The user feels the vibration and can retry their smile or adjust their position. If tracking remains unreliable, the avatar defaults to a neutral expression, allowing the user to manually select an expression using their controller.