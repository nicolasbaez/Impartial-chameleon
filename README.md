# Impartial-chameleon
Space dance

![buh](https://github.com/nicolasbaez/Rain-narwhal/blob/main/xp006.gif)
```javascript
w = 500;
h = w / 2;
k = 0;
setup = (_) => {
  createCanvas(w, w, WEBGL);
  colorMode(HSB, w);
};
draw = (_) => {
  rotateX(0.7);
  rotateY(1);
  background(0);
  for (i = -h; i < h; i += 9) {
    s = 0;
    for (j = -h; j < h; j += 9) {
      strokeWeight(2);
      stroke(s, j * noise(i) * 8, w);
      point(i, j - noise(j, i) * map(sin(k), -1, 1, -h * 8, h * 8));
      s += 10;
    }
  }
  k += 0.01;
};
function keyPressed() {
  if (key === "s") {
    saveGif("xp006.gif", 628, { delay: 0, units: "frames" });
  }
}
