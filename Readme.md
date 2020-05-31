This project showcase a simple HTML chat using WebRTC and programmed in Rust and compiled to WASM.

[Live Demo](https://codec-abc.github.io/Rust-WebRTC-p2p-Chat/)

After reading this [wonderful post](https://medium.com/leaningtech/porting-a-c-multiplayer-game-to-the-web-with-cheerp-webrtc-and-firebase-29fbbc62c5ca) by the [Cheerp team](https://leaningtech.com/pages/cheerp.html)
I wanted to see if the same can be done with "pure" Rust using WASM.

Since doing a game from scratch was too complicated as a first step I aimed to just play along with Rust, HTML (using [Yew](https://github.com/yewstack/yew)) and WebRTC by doing a chat application. 3D and WebGL will come another time.

It turns out that, while I struggle a bit here and there, it is not very difficult to get something working as you can see below:

![demo](demo.gif)

Note: If you try to run locally prefer testing with Chrome as Firefox seems to forbid connection for security purposes. 
Also, if you are testing with a friend it might not work as I am using only a STUN server. From the test I made, the connection is often blocked on corporate network and using a TURN server would solve the problem. But unlike, STUN server there aren't free servers to use.
Finally, the error handling is not totally done yet as the it is not obvious how to handle it. If you are stuck reload the page on both side and try again.

To build this project you need to:
1. Install wasm-pack with ``cargo install wasm-pack``
2. Install http-server ``cargo install http-server``

To run it once build you need to type
1. Compile code with ``wasm-pack build --target web --no-typescript --out-dir ./static/pkg``
2. Run web server in the ``static`` dir with ``http-server -p 8080`` (Alternatively you can use any static file server like ``python3 -m http.server``)

Special thanks to:
* The Rust team for making a great language
* The Yew team for making an awesome front-end framework
* [Sajad Hashemian](https://github.com/sajadhsm?tab=repositories) for making this [nice HTML chat](https://codepen.io/sajadhsm/pen/odaBdd) 