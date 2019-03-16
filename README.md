<h2><I>Dimensionality-Reduction</I></h2>
<p>My thougths and ideas about Dimensionality redcution</p>

<b>Welcome to the Dimensionality-Reduction</b>

<h3>**DIMENSIONS **</h3>

what are dimensions? A dimension can be thought of as a space where we can mark our data for comparison and visualization.To plot a single numerical variable we just need 1-D.

 * 2-D !! when we have two Continuous Numerical data related to the same study we can plot respective data points in a 2-D space to make sense out of it. We can see if the these data are independent of each other or related.This is simple co-ordinate geometry.

 * 3-D!! This is where it starts to get a bit tricky. We need 3-D space to plot to ping and visualize 3 different continuous numerical data.This is still do-able but we cant infer much from looking at a 3-D graph at first glance.We might need to rotate it and study it to make any actual sense out of it.

 * Above 3D!!? This is no-no territory for Human Brain. Our brain is only hard wired to visualize/comprehend/interpret a 3-D space. But machines can work on many dimensions and they are good at it.This is how Machine Learning was born. Machine Learning Algorithms are good with working with multi-dimensional data and classifying them in those higher dimensions!!

CURSE OF DIMENSIONALITY With all that good math and computational power ML algorithms still struggle with too many dimensions. This is because when dealing with too many dimensions our data space becomes so sparse. i.e Even when the samples are similar , they are very far apart due to too many dimensions.If you check the plot of number_of dimensions against performance of the model you can see that it increases until a certain point after which it degrades this is because data organisation methods(ML algo's) struggle in very high dimensions. eg: KNN is susceptible to overfitting due to 'CURSE OF DIMENSIONALITY'

<h2>DIMENSIONALITY REDUCTION:</h2>

<b>Einstien Said, "EVERYTHING SHOULD BE MADE SIMPLE, BUT NOT SIMPLER".</b>

This can be interpreted in our context we can try to reduce the dimensions using different methods to make our life easier for us and for our algo . But reducing the dimensions too much can lead to underfitting.

We have many ways for DIMENSIONALITY REDUCTION

<h3>PCA:</h3> The PCA transforms the original coordinate system(is a form of multidimensional scaling) and origin of this new coordinate system is located in the center of the datapoints. The new coordinates are called principal components(PC's).It is a linear transformation of the variables into a lower dimensional space with retaining maximum amount of information about the variables.

The base idea here is we are trying to capture the variance present in all of the variables in our data and make Principle components out of them that carry the most of the essence/variance of the original Data in an ordered fashion i.e PC1 captures the highest variance in the samples,later we can select top few from them as per our requirement usually we select first 2 for representation. The Math behind this involve calculation of eigen vectors out of the data that are kinda like weights.The first eigen vector forms PC1 which carries the most variance in the data i.e The first PC points in the direction of highest variance as it goes in the direction which samples exhibit maximum variation. PC2 is the second most variance/information carrying component and it is orthogonal to the PC1.

<h4>EG:<h4>

lets assume a data set like WWE like:
<table style="width:100%"><tr><th> </th><th>ATK</th><th>DEF</th><th>AGIL</th><th>RESIL</th><th>POP</th><th>W/L_Ra</th></tr>
<tr><td>randy_orton</td><td>82</td><td>85</td><td>76</td><td>74</td><td>70</td><td>0.65</td></tr>
<tr><td>John_cena</td><td>89</td><td>81</td><td>78</td><td>91</td><td>90</td><td>0.72</td></tr>
<tr><td>Brock_lesner<td>93</td><td>80</td><td>70</td><td>85</td><td>85</td><td>0.84</td></tr>
<tr><td>Chris_jer</td><td>84</td><td>86</td><td>79</td><td>72</td><td>74</td><td>0.62</td></tr>
<tr><td>Seth_rollins</td><td>90</td><td>83</td><td>82</td><td>83</td><td>88</td><td>0.77</td></tr>
<tr><td>Triple_h</td><td>85</td><td>80</td><td>83</td><td>81</td><td>83</td><td>0.71</td></tr>
<tr><td>Undertaker</td><td>89</td><td>78</td><td>75</td><td>89</td><td>92</td><td>0.74</td></tr>        
<tr><td>Rock</td><td>91</td><td>82</td><td>80</td><td>75</td><td>82</td><td>0.72</td></tr></table>

<p>Here, we have have many dimensions like attack,defence,agility,resilience,popularity,win-loss ratio now to make sense of data we try and reduce the dimensions using PCA</p>

<p>To perform PCA first we need to SCALE THE DATA!! We get PC1 and PC2 after performing PCA we can look at these as like primary components(eg: PC1(power of wrestler) PC2(weakness of wrestler) just for understanding you can think of them like this) that contain most of the essencce of the data ,they can possibly classify the wrestler</p> 
<p>Now if plot the data w.r.t PC1 and PC2 we can see that Highly correlated samples cluster!(MOST PROBABLY)</p>

<h3>Limitiations</h3>

 * There is no guarantee that the different classes are separated in the PCA-space. (e.g.if in some data the sample-to-sample variation is much higher compared to a small difference between the classes(as PCA considers only variations within samples),so in this case PCA may even level out these differences.In such cases supervised approaches are better)
 * If there are less samples than dimensions, the PCA is technically not possible.
