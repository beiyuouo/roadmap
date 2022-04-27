# Lecture 05: 渲染中光和材质的数学魔法

$$
L_{O}(\vec{x}, \vec{\omega_{o}}) = L_{e}(\vec{x}, \vec{\omega_{e}}) + \int_{H^2} f_{r}(\vec{x}, \vec{\omega_{o}}, \vec{\omega_{i}})L_{i}(\vec{x}, \vec{\omega_{i}})\cos \theta_{i} d\vec{\omega_{i}}
$$

Three challenge:

- How to get incoming radiance for any given incoming direction
- Integral of lighting and scatting function on hemisphere is expensive
- To evaluate incoming radiance, we have to compute yet another integral
