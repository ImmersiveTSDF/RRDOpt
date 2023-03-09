We sincerely thank the reviewers for their valuable comments that have aided both our present and future research. Due to word limitations, we may not be able to respond to all reviews individually. However, we have summarized the review comments and provided our responses below.

# 1.Reason for using image/video codecs instead of GPU-supported compression to compress texture maps.(R1R2R3R4R5)
Our R-RD optimization aims to contribute to the standardization of volumetric video compression being undertaken by MPEG-I (https://mpeg.chiariglione.org/standards/mpeg-i). MPEG-I is currently standardizing volumetric video compression technology using various representations (pointclouds, multiview images, and meshes) and employing video codecs (HEVC/VVC) to compress texture images. As a preprocessing technique, our method enhances the texture map compression performance of video codecs and provides significant improvements over MPEG-I's existing preprocessing methods (SPP and HBF). This is mentioned in the introduction of our main paper.

Compared to GPU-supported compression, our method prioritizes compression efficiency over real-time rendering, assuming that real-time encoding of the texture map is not necessary. However, our method does not increase decoding computation for end-users as it only operates on the encoder side. It is also designed to work without requiring modifications of codecs.

Although we acknowledge that our paper did not properly explain the scope of our research, as noted by R1's comments, we believe that our method still contributes to storing/transmitting texture data. However, we recognize the need for clarification in the revised version of our paper if given the opportunity. We also need to mention the limitations related to GPU-supported compression that we have not considered.


# 2.Reason for optimizing not only unused textures (gutters) but also used textures.
Maintaining the used textures is crucial, but it can be a drawback in terms of rate-distortion tradeoff as lossy compression may not preserve high-frequency components, leading to reduced compression performance. We modified the whole textures compression-efficiently with R-RD optimization and experiments have shown that doing so also benefits in terms of rate-rendering distortion. However, we recognize that we did not explicitly state these facts at the beginning, which may cause confusion, and we will rectify this.

We sincerely thank the reviewers for their valuable comments that have aided both our present and future research. Due to word limitations, we may not be able to respond to all reviews individually. However, we have summarized the review comments and provided our responses below.

# 3.Why is texture sampling done using bilinear interpolation?(R2R4)
We used bilinear because the results of source or novel viewpoints were good in our experience. It was also noted that alternative interpolation method can be used when describing eq.5 in the paper. Our method is compatible with various interpolation methods and is designed to reduce rendering distortion by propagating rendering error in the texel footprints of each method. However, we much agree that if views that differ greatly from source viewpoints are rendered, methods such as mipmap would be more suitable.

# 4.Results in novel viewpoints(R1R5)
We included images of arbitrary viewpoints in the appendix to the paper, but this seems to have been insufficient to address the doubts of reviewers. Our method showed good subjective quality compared to other methods in arbitral viewpoints, although we optimize the texture map by rendering distortion of source viewpoints. We will augment the validation at arbitral viewpoints through an ablation study or appendix.

# 5.Small number of tested scenes(R2R5)
Although we conducted experiments with a total of 12 texture maps by performing 3 parameterizations for each of the 4 scene models, we acknowledge that this is insufficient to ensure the reliability of the experimental results. We will add four more scenes from the previous experiment by the deadline for submitting the revised paper to ensure more reliability of the results.

# 6.Code availability(R1R3)
As reviewers say, our method is designed with a simple architecture that is easy to implement and therefore easy to reproduce. For the convenience of readers and researchers, we will release the source code of the proposed method through GitHub (include url in the paper).

# 7.Revision of the paper
## 1.Author did not focus on compression performance by showing the optimization results first in the experimental results section.(R1)
We agree to restructure the experimental results section in a logical manner. Firstly, we will provide a compression performance (bitrate and rendering quality), followed by an exploration of optimized texture maps to support the improvement in texture map compression performance achieved by our method.

## 2.Differences between images in Fig.9 (subjective quality comparison) are not imperceptible.(R4)
We will modify it to detect more distinct differences through highlights or partial magnification.

## 3.Additional introduction of related studies.
We agree to add an introduction to GPU-supported compression and texture map optimization methods for it, clarifying that our method aims to improve texture map compression efficiency on video codecs. We will also briefly mention the similarities between texture map padding and inpainting methods, emphasizing that inpainting is not carried out with compression in mind. To keep the related works section concise, we will revise it accordingly.

## 4.Redundancy of sentences and other matters
To improve readability and eliminate redundancy in our paper, we will revise sentences that overlap and shorten its length. Additionally, we will provide a brief explanation of the BD-rate calculation and the implementation framework used.

# 8. Technical issues
## 1.Another material compression(R2)
Our method takes reconstructed mesh and multiview image inputs. Extracting non-RGB materials requires sophisticated inverse rendering, which we lack expertise in. Thus, creating and compressing a texture map with other materials is challenging. Nevertheless, we expect our method to aid in compressing diverse texture maps, making it a worthwhile topic for future research.

## 2.Large Multiview dataset(R5)
Our target content is room-scale or objects captured with a camera array like MPEG-I. While we haven't focused on large datasets, we believe selecting representative viewpoints from them for R-RD optimization is a compelling extension. Nonetheless, we acknowledge the limitations of our method and will comment on the revised paper.

## 3.Rate control problem(R1)
In this paper, R-RD optimization was performed using a fixed lambda value regardless of the coding configuration. However, to improve the compression efficiency and flexibility of the proposed method, parameters like lambda should be set adaptively for the target bitrate. While this would enhance the quality of our research, rate control is a complex research area. Hence, we acknowledge this limitation in our study and will mention it as an area of future research to address.

# 9.Closing
Standard video codecs have been extensively optimized, thus, increasing their compression efficiency by 1-2% is very challenging. However, our method significantly improves compression efficiency, especially for texture map compression on video codecs. Despite its simplicity, it shows a notable improvement in texture compression performance. We believe our R-RD optimization concept can inspire other researchers. We hope to present our method at SIGGRAPH and contribute to the graphics and video compression society.

