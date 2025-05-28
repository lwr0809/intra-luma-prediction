# intra-luma-prediction


🔧 VVCSoftware VTM-23.1 Custom Configuration README

Code Platform Version Version: VVCSoftware_VTM-VTM-23.1

Macro Definitions and Functional Description 🔍 Block Partition Visualization
SPLIT_SHOW = 1
→ Enables chroma block partition visualization.

SPLIT_SHOW = 1 and SPLIT_SHOW_LUMA = 1
→ Enables luma block partition visualization.

🔶 Luma Prediction Module Test_Limit_Performance = 1, New_Softmax = 1, and RDO_COST = 1 → Enables iterative search for the optimal theta value, writes theta to the bitstream, and uses rate-distortion cost for selection.
New_Softmax = 1
→ Sets theta to -0.01 and generates CU prediction values accordingly.

Copy_block = 1
→ Enables nearest-neighbor copy along the main diagonal direction.

Template_theta = 1
→ Determines theta based on the above reconstructed CU, and uses it to generate the current CU's predicted values.

Copy_and_Planar = 1
→ Performs a weighted average between nearest-neighbor copy and planar prediction modes.

Flip_Vertical = 1
→ Enables nearest-neighbor copy along the anti-diagonal (45° upward) direction.

RDO_Flip_Vertical = 1
→ Performs rate-distortion cost comparison between Copy_block and Flip_Vertical methods, selects the optimal one, and encodes the flip flag into the bitstream.

🔷 Chroma Prediction Module Template_theta_chroma = 1
→ Determines theta from the above reconstructed CU, and uses it to generate chroma prediction values for the current CU.
Softmax_chroma = 1
→ Sets theta to -1 and uses it to generate chroma prediction values.
