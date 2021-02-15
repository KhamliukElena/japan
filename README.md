# japan

I got an ispiration for this project from Nonogram.com ( https://play.google.com/store/apps/details?id=com.easybrain.nonogram&hl=ru&gl=US ). The idea is the same with some minor corrections. I plan to add ? sign in addition to square and x signs to mark cells, which require further investigation.
Due to attempt in adaptivity I plan to add a switch to replace right mouse button click for mobile devices.]

What's more planned for implementation:

1. Add check if a cell of a game field has already been visited not to process it several times;
2. Switch for different types of clicks and add it into cell check processtion;
3. Add reading level information from a .json file instead of hard coding.
4. Add "levels" wiget to be able to switch between levels;
5. Think about level information transmition and reading: should component "Field" process it? Consider vuex for data exchange;
6. Validate information about level in component "Field".

I will update this readme when these features are implemented.
