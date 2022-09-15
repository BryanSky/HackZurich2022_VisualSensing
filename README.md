## Challenge - Visual Sensing & Vehicle Health

Superficial damage to the tires, body and undercarriage of a commercial vehicle is a problem to a fleet, causing unforeseen costs or in the worst case leading to more critical problems if not resolved. Automated visual inspection can help catch these damages, but what does the interface between this automated system and the fleet manager look like?

<!--![image](https://user-images.githubusercontent.com/113338125/189901942-7b4d55a8-438f-49fe-8a7d-d052503feeff.png)-->


Fleet Managers are operating on a tiny margin and a large source of their costs are on unplanned breakdowns and fines.
An Automated Inspection Program at a yard to perform pre- and post trip vehicle inspection can optimize the operation costs.
Let's imagine that fleets' trucks undergo a quick inspection at Yard's gate while entering. Then its drivers don't have extra responsibilities and the fleet manager is alerted of any issues or broken parts before they become issues.

<img src="https://user-images.githubusercontent.com/113338125/190394597-77b36cb2-0286-4b4f-8a45-50cc4d26f934.png"  width="600">

Potentially the visual inspection of the vehicles can be done at the yard with an autonomous robotic arm which operates continuosly at yard level. 
Here the main task is to build a workflow from i) image capturing, toward ii) vehicle part and damages identification, and iii) UX design on how the fleet manager can make use of such a tool to optimize the fleet operation.

Here you can see example of an algorithm detecting driver, headlights, license plate, and auxiliary mirror. This is a first step toward the vehicle inspection, i.e., the vehicles' parts need to be well identified by the algorithm in order to detect any possible superficial damages on it. 

<img src="https://user-images.githubusercontent.com/113338125/190345413-9252b56c-db41-4791-902b-e058ca788f4a.png"  width="400">

In the following you see how the UX for an end user (fleet manager) might look like in a first place to demonstrate all the vehicles' parts and their status. 

<img src="https://user-images.githubusercontent.com/113338125/190345509-9e861d4e-558a-4358-999b-9e114f518495.png"  width="600">


### Problem statement 

*Question:* How might we assist a fleet manager to better monitor and manage the status of their vehicles?

*Challenge:* Develop a concept that assists a fleet manager to better understand and digitally sense the health of the fleet.

*Hints:*
- Focus on identifying the right customer problem to solve, rather than jumping straight into the technical solution.
- Consider similar approaches in other industries, could that work for this topic?



### Data provided

Here we provide series of annotated image dataset from vehicle damages. Annotation information includes the coordinates of bounding boxes and polygons of the car damage in the images. The annotation is in two folds:
- In files "COCO_train_annos.json" (for training) and "COCO_val_annos.json" (for validation), _damage_ is the only category. It includes coordinations of all bounding boxes of damages in the image. The sample is shown below:
<img src="https://user-images.githubusercontent.com/113338125/190369823-bac748f6-ab28-4509-822a-eb31ce506186.png"  width="400">

- In files "COCO_mul_train_annos.json" (for training) and "COCO_mul_val_annos.json" (for validation), five categories namely _headlamp, front bumper, hood, door, rear bumper_ are annotated with coordinates of bounding boxes of the vehicle part identified in the image. The sample is shown below:
<img src="https://user-images.githubusercontent.com/113338125/190369875-9e7a4046-d2c3-42e1-93d5-58ecb4fe30b9.png"  width="400">

The annotations are from: 
- 61 images for training (with annotations of "COCO_train_annos.json" and "COCO_mul_train_annos.json"), 
- 11 images for validation 11 (with annotations "COCO_val_annos.json" and "COCO_mul_val_annos.json").


For your ease and knowing that training a model from scratch is especially expensive, we provide a notebook with a pretrained detection model of [Detectron 2](https://github.com/facebookresearch/detectron2), which refines the model with the annotated **COCO** dataset mentioned above. 
To achieve the goal of recognizing which part of a vehicle is damaged, a possible solution is using two models which is used in the notebook. 
First model is trained for detecting damages in the image, whose output is the coordinates of the damages in the image. Second model is developed to segment the vehicle's parts shown in the image, e.g., hood, door, bumper, and output the coordinates of the car parts. After obtaining the locations of damages and locations of all car parts in the image, we used the results to detect which part is damaged in the vehicle. 
<img src="https://user-images.githubusercontent.com/113338125/190371487-aa4e8648-915c-458d-91df-a7112a25c79c.png"  width="400">

For testing the result of the algorithm (as deliverable) we provide:
- Test images (~700 images)
- Labeled on damage part (Test_damage_labeled.xlsx)



### Goal 
Design an end-to-end pipeline that is capable of capturing images, detecting damages, and presenting this info to the fleet manager. The solution should serve a fleet manager to catch damages sooner, and provide more insight into this aspect of their operations. Take a look at the example below:

<img src="https://user-images.githubusercontent.com/113338125/190353635-86a9b768-bd47-465e-b3b1-f5464e1aad59.png"  width="600">

It contains a dashboard on a type of analysis a fleet manager can review and guided through tangible actions. You task is to wireframe the process and storyline for an actionable decision making process and mock them up in few steps.


### Our expectation
- Presentation with a clear problem statement & solution definition (a business opportunity potentially supported by market demand).
- Provide Illustration of results as much as possible.
- Mockup/wireframe of digital solution for a fleet manager with a prescriptive / decision making feature.




### Downloads
Downloads will be made available during the workshops on Friday, Sept 16. Stay tuned!

We look forward to working with you at the HackZurich 2022!

You have questions, ideas for your own project, or just want to chat with us? Reach out on DISCORD channel #19-zf or directly at our booth.
