# Alignment
![Try to fly in the same average heading of your cohort](image/alignment.gif)

Aligning yourself in the average heading of your cohort is an other motivation.

## Calculation
Instead of working on the position of our cohort of boids, we are working with
the headings. Let the heading of our boids be given by a sequence
\\(h_{1}, h_{2},\ldots,h_{n}\\).

We would like to align our heading with the average of the heading in our
cohort. The average is calculated by

\\[
h := \frac{1}{n} \sum_{i=1}^{n} h_{i}
\\]

This is the heading our boid needs to move in if she wants to align herself to
her cohort.
