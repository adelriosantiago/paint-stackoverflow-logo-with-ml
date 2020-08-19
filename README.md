To run in localhost:

- `npm install -global http-server`
- `http-server` on this directory
- Open index.html

Insipired in: http://caza.la/synaptic/#/paint-an-image

StackOverflow question: [link]

---

# How to improve accuracy of a Feedforward Neural Network (FFNN)?

I want to train a Neural Network to draw StackOverflow's logo:

![](./so.bmp)

For simplicity, this logo is 125 width by 125 height BMP at 255 colors.

To do so, I have this created this simple Feedforward Neural Network architecture:

![](./architecture.jpg)

This FFNN has 2 inputs, 15 hidden layers and 3 outputs. Inputs are the X, Y coordinates of a pixel. The three outputs are the RGB colors of that pixel.

The NN should ideally become *[r, g, b] = f([x, y])*. In other words, it should return RGB colors for a given pair of coordinates. The FFNN works pretty well for simple shapes like a circle or a box. The result after several thousands epochs looks pretty well:

![](./circle-result.jpg)

Try it yourself:

[snippet]

However since StackOverflow's logo is far more complex even after several thousands of iterations the FFNN's results are somewhat poor:

![](./so-result.jpg)

Try it yourself: [snippet]

From left to right:

 1. With 15 hidden neurons: The left handle never appears.
 2. 50 hidden neurons: Pretty poor result in general.
 3. 0.03 as learning rate: Shows blue in the results (blue is not in the orignal image)
 4. A time-decreasing learning rate: The left handle appears but other details are now lost.

The question is: **In general, how can I improve the accuracy of a FFNN?**

Could you modify the snippet with better results? Is a FFNN even capable of achieving good drawing results? If there is a better NN architeture could you provide an example?

 - Artificial Neural Network library used: [Synaptic.js](https://caza.la/synaptic/)
 - To run this example in your localhost: [See repository](https://github.com/adelriosantiago/paint-stackoverflow-logo-with-ml)