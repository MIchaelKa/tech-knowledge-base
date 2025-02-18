
Andrej Karpathy

Moved
- https://www.notion.so/A-Recipe-for-Training-Neural-Networks-c2c461c42eae47e3996f9215064ee2d3

Links
- http://karpathy.github.io/2019/04/25/recipe/


Takeaways
- if low-level details don’t matter much try to input a smaller image
- use backprop to chart dependencies

Things you can try
- Set the bias on your logits

Questions
- off-by-one bug
- clip your gradients but instead clipped the loss
- very local features enough or do we need global context?
- “hockey stick” loss curves