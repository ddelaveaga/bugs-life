# Bugs Life

An interactive 3D animation project built with Three.js featuring bugs exploring a grassy field.

## Features

- Two animated bugs (red ladybug and yellow bee) that explore a procedurally generated field
- Realistic collision detection and physics when bugs bump into each other
- Multiple camera views including first-person perspectives from each bug
- Day/night cycle with dynamic lighting
- Interactive controls for speed adjustment and camera switching
- Particle effects during bug collisions
- Responsive design that works on desktop and mobile devices

## Demo

Visit the [live demo](https://github.com/ddelaveaga/bugs-life) to see the animation in action.

## Getting Started

### Prerequisites

- A modern web browser
- Node.js and npm (for running the local server)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/ddelaveaga/bugs-life.git
cd bugs-life
```

2. Start a local server:
```bash
npx http-server -p 8080 --cors
```

3. Open your browser and navigate to:
```
http://localhost:8080/bug-field.html
```

## Controls

- **Speed Slider**: Adjust how fast the bugs move
- **Toggle Camera View**: Switch between normal and top-down views
- **Toggle Day/Night**: Switch between day and night lighting
- **Red Bug's View**: See the world from the red bug's perspective
- **Yellow Bug's View**: See the world from the yellow bug's perspective

## Technologies Used

- [Three.js](https://threejs.org/) - 3D JavaScript library
- HTML5 & CSS3
- JavaScript (ES6+)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Three.js community for their excellent documentation and examples
- Inspiration from nature and the fascinating world of insects

# three.js

[![NPM Package][npm]][npm-url]
[![Build Size][build-size]][build-size-url]
[![NPM Downloads][npm-downloads]][npmtrends-url]
[![DeepScan][deepscan]][deepscan-url]
[![Discord][discord]][discord-url]

#### JavaScript 3D library

The aim of the project is to create an easy-to-use, lightweight, cross-browser, general-purpose 3D library. The current builds only include WebGL and WebGPU renderers but SVG and CSS3D renderers are also available as addons.

[Examples](https://threejs.org/examples/) &mdash;
[Docs](https://threejs.org/docs/) &mdash;
[Manual](https://threejs.org/manual/) &mdash;
[Wiki](https://github.com/mrdoob/three.js/wiki) &mdash;
[Migrating](https://github.com/mrdoob/three.js/wiki/Migration-Guide) &mdash;
[Questions](https://stackoverflow.com/questions/tagged/three.js) &mdash;
[Forum](https://discourse.threejs.org/) &mdash;
[Discord](https://discord.gg/56GBJwAnUS)

### Usage

This code creates a scene, a camera, and a geometric cube, and it adds the cube to the scene. It then creates a `WebGL` renderer for the scene and camera, and it adds that viewport to the `document.body` element. Finally, it animates the cube within the scene for the camera.

```javascript
import * as THREE from 'three';

const width = window.innerWidth, height = window.innerHeight;

// init

const camera = new THREE.PerspectiveCamera( 70, width / height, 0.01, 10 );
camera.position.z = 1;

const scene = new THREE.Scene();

const geometry = new THREE.BoxGeometry( 0.2, 0.2, 0.2 );
const material = new THREE.MeshNormalMaterial();

const mesh = new THREE.Mesh( geometry, material );
scene.add( mesh );

const renderer = new THREE.WebGLRenderer( { antialias: true } );
renderer.setSize( width, height );
renderer.setAnimationLoop( animate );
document.body.appendChild( renderer.domElement );

// animation

function animate( time ) {

	mesh.rotation.x = time / 2000;
	mesh.rotation.y = time / 1000;

	renderer.render( scene, camera );

}
```

If everything goes well, you should see [this](https://jsfiddle.net/v98k6oze/).

### Cloning this repository

Cloning the repo with all its history results in a ~2 GB download. If you don't need the whole history you can use the `depth` parameter to significantly reduce download size.

```sh
git clone --depth=1 https://github.com/mrdoob/three.js.git
```

### Change log

[Releases](https://github.com/mrdoob/three.js/releases)


[npm]: https://img.shields.io/npm/v/three
[npm-url]: https://www.npmjs.com/package/three
[build-size]: https://badgen.net/bundlephobia/minzip/three
[build-size-url]: https://bundlephobia.com/result?p=three
[npm-downloads]: https://img.shields.io/npm/dw/three
[npmtrends-url]: https://www.npmtrends.com/three
[deepscan]: https://deepscan.io/api/teams/16600/projects/19901/branches/525701/badge/grade.svg
[deepscan-url]: https://deepscan.io/dashboard#view=project&tid=16600&pid=19901&bid=525701
[discord]: https://img.shields.io/discord/685241246557667386
[discord-url]: https://discord.gg/56GBJwAnUS

