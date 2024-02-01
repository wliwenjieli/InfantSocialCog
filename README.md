# A Machine Social Reasoning Benchmark Inspired by Infants Cognition
## Supplementary background training set 

Infants bring knowledge to developmental tasks, unlike deep learning systems that start with much more limited inductive biases. We provide a background training set to offer machines a learning opportunity. This set serves two purposes: 
First, to present elements of the environment and task setup. This understanding is essential to solve the benchmark, but irrelevant to social cognition. 
Second, it introduces the cognitive abilities required to succeed at the evaluation tasks. These training tasks are carefully designed to contain low-level visual signals and movement patterns that are distinct from the evaluation tasks, preventing trivial task solution through pattern matching.

![bgtasks](https://github.com/wliwenjieli/InfantSocialCog/assets/44118444/12ab727b-437e-4faa-a639-8d167b7f976f)

Figure 1. Overview of the Background Training Set. Like the evaluation set, each background training episode includes eight familiarization trials followed by one test trial. Notably, similar to infants' experiences, there are no negative examples in the training set. While it is challenging to match the complexity of infants' real-world experiences, we believe this training set offers a limited yet reasonable foundation for meaningful comparison. We encourage the usage of additional data sources to enhance machines' performance. 

### (a) Occlusion: Object Collection
Similar to Single Object Collect (e), this task (Figure 1a) includes an additional spinner in the environment that does not interact with the agent. A grey square-shaped occluder appears under all elements in familiarization and above at the last trial.

### (c) Occlusion: No-Navigation Preference 
As illustrated in Figure 1c, an agent consistently chooses between two proximal target objects, with varying locations across trials, to emphasize object-based over location-based goals. Upon contact, both objects change color, eliciting cues for causal efficacy that distinguish goal-approach behavior from a pro-social approach. A spinning object is in the scene, away from the agent. A grey square-shaped occluder lays under all elements in familiarization and on top of them at test time.

### (d) Occlusion: No-Navigation Bouncing Object
As shown in Figure 1d, a rotating spinner propels an element toward one of two target objects, which change color upon contact. The target object varies between trials, depending on the spinner's initial rotation and the element's position, illustrating that passive movement driven by another object does not necessarily signify goal preference.

### (e) Single Object Collect
An agent navigates through obstacles to reach a single target object, which changes color upon contact (Figure 1e). This task demonstrates obstacle navigation and goal pursuit. In some but not all episodes, the agent returns to the starting point after interacting with the object.

### (f) Moving Object 
As shown in Figure 1f, an agent approaches a goal object and picks it up, which is illustrated with the agent on top and in the center of the object. The agent and object pair then travel together to a different location. After they stop moving, the agent drops off the object. This task shows how an object can be picked up and moved around by an agent in the environment. 

### (g) & (h) No-Navigation Approach: Instrumental & Social 
This task involves three agents and a goal object (Figure 1gj). In the familiarization phase, an agent consistently approaches one of two stationary agents in proximity, demonstrating a social affiliation. At test time, the two previously stationary agents each move in a unique movement. Following that, the previously approaching agent also performs a movement. In No-Navigation Approach: Social, this movement is identical to that of the approached agent in familiarization. In No-Navigation Approach: Instrumental, the movement is identical to one of the other two agents which was not necessarily approached before. In addition, only in instrumental conditions does the agent interact with a goal object at the end of the move, causing it to change color. The route taken is the only efficient path to the goal object, cueing a goal-directed behavior. 

### (i) & (l) Trapped Agent: Helping & Hindering
This task (Figure 1il) uses a similar setup as the Helping and Hindering tasks in evaluation. However, the locations of the goal-directed agent and the goal object are swapped. In Helping (Figure 4i), a social agent helps move away an obstacle to allow the main agent to approach its goal object while the other social agent watches. In Hindering (Figure 4l), a social agent blocks the goal-directed agent from approaching its goal while the other social agent watches. At test time, the goal-directed agent approaches the agent who helps in the helping condition and the agent who watches instead of obstructing its goal in the hindering condition.

### (h) & (k) No-Relocation: False & True Belief 
This task features an occluder that may or may not appear between a goal-directed agent and its goal. Specifically, it is always in between on the first familiarization trial, obstructing the agent from identifying the side of the room where the goal is located. The agent randomly enters a room and either succeeds in or fails to find the goal object, giving machines an opportunity to learn that the occluder interferes with the perception of the rational goal-directed agent. If the agent finds the goal object in the first familiarization trial, it would consistently go to the same side of the room to find the object in the later familiarization trials, where the occluder randomly shows up between the agent and object or behind the environment. If the agent did not find the goal object in the first familiarization, it would later consistently go to the other side of the room to find the goal object. This task communicates two assumptions: 1) the agent believes a goal object is always at where it was last seen. 2) if the goal object is absent on one side of the room, it must be on the other side. At test time, a different agent moves the goal object around within the same room, either in the presence or absence of the first agent. The task then shows the initial agent returning to the same room to retrieve the goal object.
