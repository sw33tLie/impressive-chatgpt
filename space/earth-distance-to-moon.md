# Input

can you write a script to calculate earth distance to moon?


# Answer

Yes, here is a simple script that calculates the distance between the Earth and the Moon:

```bash
#include <stdio.h>
#include <math.h>

int main()
{
    // Earth and Moon coordinates
    double x1 = 1.0, y1 = 0.0, z1 = 0.0;
    double x2 = -1.0, y2 = 0.0, z2 = 0.0;

    // Calculate the distance between the Earth and the Moon
    double distance = pow(pow(x1 - x2, 2) + pow(y1 - y2, 2) + pow(z1 - z2, 2), 0.5);

    // Print the distance
    printf("The distance between the Earth and the Moon is %f\n", distance);

    return 0;
}
```

In this script, the Earth and Moon are assumed to be located at fixed positions in space. In reality, their positions would change over time due to their orbits around the Sun. To calculate the distance between the Earth and the Moon at a specific point in time, you would need to take into account the position of the Earth and Moon at that time, which would require more complex calculations.
