We sincerely thank the reviewers for their valuable comments that have aided both our present and future research. Due to word limitations, we may not be able to respond to all reviews individually. However, we have summarized the review comments and provided our responses below.

# 1.Reason for using image/video codecs instead of GPU-supported compression to compress texture maps.(R1R2R3R4R5)


Our R-RD optimization aims to contribute to the standardization of volumetric video compression being undertaken by MPEG-I (https://mpeg.chiariglione.org/standards/mpeg-i). MPEG-I is currently standardizing volumetric video compression technology using various representations (pointclouds, multiview images, and meshes) and employing video codecs (HEVC/VVC) to compress texture images. As a preprocessing technique, our method enhances the texture map compression performance of video codecs and provides significant improvements over MPEG-I's existing preprocessing methods (SPP and HBF). This is mentioned in the introduction of our main paper.

Compared to GPU-supported compression, our method prioritizes compression efficiency over real-time rendering, assuming that real-time encoding of the texture map is not necessary. However, our method does not increase decoding computation for end-users as it only operates on the encoder side. It is also designed to work without requiring modifications of codecs.

Although we acknowledge that our paper did not properly explain the scope of our research, as noted by R1's comments, we believe that our method still contributes to storing/transmitting texture data. However, we recognize the need for clarification in the revised version of our paper if given the opportunity. We also need to mention the limitations related to GPU-supported compression that we have not considered.


