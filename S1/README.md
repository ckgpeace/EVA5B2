1. What are Channels and Kernels (according to EVA)?

	• Channels in CNN contain a set of particular features. In a typical CNN initial channels contain preliminary features like edges and later channels contain more complex features like pattern and objects. We can think of channels as these hold many different features of an image which can be combined to recreate the image itself. A particular set of channels holds a particular  set of feature. 
		○ A more generic example is that we can record sounds from 4 different musical instruments separately in a live show. Each particular set of recording have one instrument in a file. Guitar channel contains guitar, tabla channel contains tabla sound, flute channel contain flute sound and piano channel contains piano sound. But we can mix these channels to recreate the live music.
	• Kernels are also called feature extractors. Kernels are basically feature finder, they look into the coming image and tries to find a particular feature in the by convolving over the image. Kernels extract features from the incoming image and after full convolution over that image creates the channel of that particular feature
		○ A kernel extracting horizontal lines in an image extract all horizontal lines in that image and a channel for horizontal lines.


2. Why should we (nearly) always use 3x3 kernels?
	1. 3X3 kernels are fast and efficient
	2. These kernels are odd which in other sense can be used to detect particular features while convolving due its symmetry around the center axis. An even number kernel does not have this specialty
	3. Combining kernels of 3x3 can similar set of features with less number of parameters. The output of one 11x11 kernel can be mimicked by five 3x3 kernels. The total number of parameters per kernel is 121 vs 45 i.e. almost 3 times lesser
	4. There is hardware implementation as NVIDIA is making 3X3 kernels faster and mostly whole community till date is super fine with 3x3 kernels
	
3. How many times to we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 (type each layer output like 199x199 > 197x197...)
	
  • 99 times
  
	199  x  199  -> 	3x3 ->	197  x  197
	197  x  197  -> 	3x3 ->	195  x  195
	195  x  195  -> 	3x3 ->	193  x  193
	193  x  193  -> 	3x3 ->	191  x  191
	191  x  191  -> 	3x3 ->	189  x  189
	189  x  189  -> 	3x3 ->	187  x  187
	187  x  187  -> 	3x3 ->	185  x  185
	185  x  185  -> 	3x3 ->	183  x  183
	183  x  183  -> 	3x3 ->	181  x  181
	181  x  181  -> 	3x3 ->	179  x  179
	179  x  179  -> 	3x3 ->	177  x  177
	177  x  177  -> 	3x3 ->	175  x  175
	175  x  175  -> 	3x3 ->	173  x  173
	173  x  173  -> 	3x3 ->	171  x  171
	171  x  171  -> 	3x3 ->	169  x  169
	169  x  169  -> 	3x3 ->	167  x  167
	167  x  167  -> 	3x3 ->	165  x  165
	165  x  165  -> 	3x3 ->	163  x  163
	163  x  163  -> 	3x3 ->	161  x  161
	161  x  161  -> 	3x3 ->	159  x  159
	159  x  159  -> 	3x3 ->	157  x  157
	157  x  157  -> 	3x3 ->	155  x  155
	155  x  155  -> 	3x3 ->	153  x  153
	153  x  153  -> 	3x3 ->	151  x  151
	151  x  151  -> 	3x3 ->	149  x  149
	149  x  149  -> 	3x3 ->	147  x  147
	147  x  147  -> 	3x3 ->	145  x  145
	145  x  145  -> 	3x3 ->	143  x  143
	143  x  143  -> 	3x3 ->	141  x  141
	141  x  141  -> 	3x3 ->	139  x  139
	139  x  139  -> 	3x3 ->	137  x  137
	137  x  137  -> 	3x3 ->	135  x  135
	135  x  135  -> 	3x3 ->	133  x  133
	133  x  133  -> 	3x3 ->	131  x  131
	131  x  131  -> 	3x3 ->	129  x  129
	129  x  129  -> 	3x3 ->	127  x  127
	127  x  127  -> 	3x3 ->	125  x  125
	125  x  125  -> 	3x3 ->	123  x  123
	123  x  123  -> 	3x3 ->	121  x  121
	121  x  121  -> 	3x3 ->	119  x  119
	119  x  119  -> 	3x3 ->	117  x  117
	117  x  117  -> 	3x3 ->	115  x  115
	115  x  115  -> 	3x3 ->	113  x  113
	113  x  113  -> 	3x3 ->	111  x  111
	111  x  111  -> 	3x3 ->	109  x  109
	109  x  109  -> 	3x3 ->	107  x  107
	107  x  107  -> 	3x3 ->	105  x  105
	105  x  105  -> 	3x3 ->	103  x  103
	103  x  103  -> 	3x3 ->	101  x  101
	101  x  101  -> 	3x3 ->	99  x  99  
	99  x  99  -> 	3x3 ->	97  x  97  
	97  x  97  -> 	3x3 ->	95  x  95  
	95  x  95  -> 	3x3 ->	93  x  93  
	93  x  93  -> 	3x3 ->	91  x  91  
	91  x  91  -> 	3x3 ->	89  x  89  
	89  x  89  -> 	3x3 ->	87  x  87  
	87  x  87  -> 	3x3 ->	85  x  85  
	85  x  85  -> 	3x3 ->	83  x  83  
	83  x  83  -> 	3x3 ->	81  x  81  
	81  x  81  -> 	3x3 ->	79  x  79  
	79  x  79  -> 	3x3 ->	77  x  77  
	77  x  77  -> 	3x3 ->	75  x  75  
	75  x  75  -> 	3x3 ->	73  x  73  
	73  x  73  -> 	3x3 ->	71  x  71  
	71  x  71  -> 	3x3 ->	69  x  69  
	69  x  69  -> 	3x3 ->	67  x  67  
	67  x  67  -> 	3x3 ->	65  x  65  
	65  x  65  -> 	3x3 ->	63  x  63  
	63  x  63  -> 	3x3 ->	61  x  61  
	61  x  61  -> 	3x3 ->	59  x  59  
	59  x  59  -> 	3x3 ->	57  x  57  
	57  x  57  -> 	3x3 ->	55  x  55  
	55  x  55  -> 	3x3 ->	53  x  53  
	53  x  53  -> 	3x3 ->	51  x  51  
	51  x  51  -> 	3x3 ->	49  x  49  
	49  x  49  -> 	3x3 ->	47  x  47  
	47  x  47  -> 	3x3 ->	45  x  45  
	45  x  45  -> 	3x3 ->	43  x  43  
	43  x  43  -> 	3x3 ->	41  x  41  
	41  x  41  -> 	3x3 ->	39  x  39  
	39  x  39  -> 	3x3 ->	37  x  37  
	37  x  37  -> 	3x3 ->	35  x  35  
	35  x  35  -> 	3x3 ->	33  x  33  
	33  x  33  -> 	3x3 ->	31  x  31  
	31  x  31  -> 	3x3 ->	29  x  29  
	29  x  29  -> 	3x3 ->	27  x  27  
	27  x  27  -> 	3x3 ->	25  x  25  
	25  x  25  -> 	3x3 ->	23  x  23  
	23  x  23  -> 	3x3 ->	21  x  21  
	21  x  21  -> 	3x3 ->	19  x  19  
	19  x  19  -> 	3x3 ->	17  x  17  
	17  x  17  -> 	3x3 ->	15  x  15  
	15  x  15  -> 	3x3 ->	13  x  13  
	13  x  13  -> 	3x3 ->	11  x  11  
	11  x  11  -> 	3x3 ->	9  x  9
	9  x  9  -> 	3x3 ->	7  x  7
	7  x  7  -> 	3x3 ->	5  x  5
	5  x  5  -> 	3x3 ->	3  x  3
	3  x  3  -> 	3x3 ->	1  x  1

4. How are kernels initialized?

	• Kernels are initialized using random values as initializing using fixed values would be inefficient. This would be inefficient as fixed values would take longer to converge as all the search would be initiated from a fixed value and it gives a hard start for all searches but the optimized parameters could possibly be anywhere in the given search space. 
	• A random initialization covers the search space in a more efficient way as the random values spread normally across the search space and hence help finding the optimum values faster as compared to fixed values
	
5. What happens during the training of a DNN?

	1. Input: The input is the data, in case of CV its mostly image. It can be in format. Its needed to convert those images in a way it can be fed to the CNN or NN or DNN
	2. Hidden CNN Layers: These layers consists of various channels. Each channel has its own kernel. Each kernel has specific task to extract features from the incoming image
		a. All the kernels are randomly initialized. All these randomly initialized parameters will get optimized while we train out network
		b. The total number of layers depends on factors as input image resolution, image size, receptive field of network, accuracy required, training time, hardware resources available, complexity of training task, size of training data etc.
		c. Receptive field of the final network should cover the whole image i.e. final layers of the network should have whole view of the image
	3. Fully Connected layer: FC layers are used for the final prediction using softmax function or other transformation
	4. Training out DNN: 
		a. Image get fed into the designed DNN, kernels extract features, fully connected layer gets input from CNN layer, output is generated
		b. Loss is calculated based on the difference between actual and predicted value
		c. Next step is to reduce this loss so that predictions come closer to actuals
		d. The loss is being reduced using back propagation [ this is the key to DNN but never bother us in implementation, we just need to write forward network, backward is taken care by pytorch, tensorflow etc.]
		e. The network is trained till our time or resource or our patience is exhausted. All the parameters are updated in each pass.
		f. There are million other things that we need take care:
			i. Learning rate
			ii. Overfitting
			iii. Validation
			iv. Vanishing gradient etc.
	5. Once DNN stops training after we achieve the desired result, DNN just takes a deep breathe and becomes cool and the parameters freeze. These parameters can be used to perform task on unseen data
			
		
