python version: 2.7

1.to implement MDDT run main.py

2. most of the data sets used in the paper come from https://github.com/vlosing/driftDatasets/
   due to the upload limit of github, we only supplement three excluded data sets: sine1, sine2, stagger(foked from  https://github.com/alipsgh/data_streams

# driftDatasets

## Artificial:

#### [SEA Concepts] (https://github.com/vlosing/driftDatasets/tree/master/artificial/sea)
This dataset consists of 50000 instances with three attributes of which only two are relevant.
The two class decision boundary is given by f<sub>1</sub> + f<sub>2</sub> = b, where f<sub>1</sub>, f<sub>2</sub> are the two relevant features and b a predefined threshold.
Abrupt drift is simulated with four different concepts, by changing the value of b every 12500 samples.
Also included are 10\% of noise.

#### [Rotating Hyperplane] (https://github.com/vlosing/driftDatasets/tree/master/artificial/hyperplane)
A hyperplane in d-dimensional space is continuously changed in position and orientation continuous addition.
We used the Random Hyperplane generator in MOA with the same parametrization as in [PAW] (https://users.ics.aalto.fi/jesse/papers/article2_SAC.pdf) (10 dimensions, 2 classes, delta=0.001).

#### [Moving RBF] (https://github.com/vlosing/driftDatasets/tree/master/artificial/rbf)
Gaussian distributions with random initial positions, weights and standard deviations are moved with constant speed v in d-dimensional space. The weight controls the partitioning of the examples among the Gaussians.
We used the Random RBF generator in MOA with the same parametrization as in [PAW] (https://users.ics.aalto.fi/jesse/papers/article2_SAC.pdf) (10 dimensions, 50 Gaussians, 5 classes, v=0.001).

#### [Interchanging RBF] (https://github.com/vlosing/driftDatasets/tree/master/artificial/rbf)
Fifteen Gaussians with random covariance matrices are replacing each other every 3000 samples. Thereby, the number of Gaussians switching their position increases each time by one
until all are simultaneously changing their location. This allows to evaluate an algorithm in the context of abrupt drift with increasing strength. Altogether 67 abrupt drifts are occurring within this dataset.

#### [Moving Squares] (https://github.com/vlosing/driftDatasets/tree/master/artificial/movingSquares)
Four equidistantly separated, squared uniform distributions are moving in horizontal direction with constant speed. The direction is inverted whenever the leading square reaches a predefined boundary.
Each square represents a different class. 
The added value of this dataset is the predefined time horizon of 120 examples before old instances may start to overlap current ones. This is especially useful for dynamic sliding window approaches, allowing to test whether the size is adjusted accordingly.


## Real World:

#### [Weather] (https://github.com/vlosing/driftDatasets/tree/master/realWorld/weather) ([original source] (http://users.rowan.edu/~polikar/research/nse/))
Elwell et al. introduced this dataset. In the period of 1949-1999 eight different features such as temperature, pressure wind speed etc. were measured at the Offutt Air Force Base in Bellevue, Nebraska. 
The target is to predict whether it is going to rain on a certain day or not.
The dataset contains 18159 instances with an imbalance towards no rain (69%).

#### [Electricity market dataset] (https://github.com/vlosing/driftDatasets/tree/master/realWorld/Elec2) ([original source] (http://www.inescporto.pt/~jgama/ales/ales_5.html))
This problem is often used as a benchmark for concept drift classification. Initially described by Harris et al. it was used thereafter for several performance comparisons. 
A critical note to its suitability as a benchmark can be found in.
The dataset holds information of the Australian New South Wales Electricity Market, whose prices are affected by supply and demand. Each sample, characterized by attributes such as day of week, time stamp, market demand etc., refers to a period of 30 minutes and the class label identifies the relative change (higher or lower) compared to the last 24 hours.
We used the normalized version as it also can be found [here] (http://moa.cms.waikato.ac.nz/datasets/).

#### [Forest Cover Type] (https://github.com/vlosing/driftDatasets/tree/master/realWorld/covType) ([original source] (https://archive.ics.uci.edu/ml/datasets/Covertype))
Assigns cartographic variables such as elevation, slope, soil type, ... of 30 x 30 meter cells to different forest cover types. Only forests with minimal human-caused disturbances were used, so that resulting forest cover types are more a result of ecological processes. It is often used as a benchmark for drift algorithms. We used the normalized version as it also can be found [here] (http://moa.cms.waikato.ac.nz/datasets/).

#### [Poker Hand] (https://github.com/vlosing/driftDatasets/tree/master/realWorld/poker) ([original source] (https://archive.ics.uci.edu/ml/datasets/Poker+Hand))
One million randomly drawn poker hands are represented by five cards each encoded with its suit and rank. The class is the resulting poker hand itself such as one pair, full house and so forth.
This dataset has in its original form no drift, since the poker hand definitions do not change and the instances are randomly generated. However, we used the version presented in [PAW] (https://users.ics.aalto.fi/jesse/papers/article2_SAC.pdf), in which virtual drift is introduced via sorting the instances by rank and suit. Duplicate hands were also removed.
We used the normalized version as it also can be found [here] (http://moa.cms.waikato.ac.nz/datasets/).