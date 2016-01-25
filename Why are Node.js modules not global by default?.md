To avoid dependency hell.

The most awesome thing about npm is that if you depend on version 2 of package A, and you require package B, which depends on version 1 of package A, it will work! Automatically! B will use A1 and your main app will use A2, simultaneuosly.

If packages were global, this would break, and you would effectively be barred from using package B (if you are so lucky as to have that option - if you're dependent on it, you can never upgrade your main app to A2)

Global packages are sort-of supported with peerDependencies, and let me tell you, as a person that has worked extensively with them, that they are almost always horrible to work with. If you can avoid it in any way, don't create a module that needs to maintain global state, it will only lead to a world of hurt.

Taken from: https://www.quora.com/Why-are-Node-js-modules-not-global-by-default
