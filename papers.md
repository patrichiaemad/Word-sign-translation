
# Paper 1

- The proposed ASLR system uses a SU-based approach to recognition, different from the majority of DL-based systems that work with word models.
- It employs a non-end-to-end learning approach and utilizes hand features embedded within a trajectory space.
- This approach endows the SUs with phonological meaning, making them both data-driven and semantically meaningful.
- The system includes four SU networks running in parallel and a second-level network for sign recognition.
- The parallel approach is used to better handle the multi-modal and concurrent characteristics prevalent in signing activity.
- The proposed approach differs from other DL-based works that typically perform end-to-end training of the network and lack interpretability.

# Paper 2

- The paper proposes a novel time domain graph convolutional network model (TGCN) for multiple objects tracking
- TGCN uses a data-driven graph convolutional architecture for time domain pose representation and learning
- Experimental results on the MOT16 benchmark show that TGCN is a strong competitor to current multiple objects tracking approaches
- Future plans include using TGCN for other computer vision tasks such as Re-ID.

# Our Paper

- The paper introduces a new large-scale Word-Level American Sign Language (WLASL) dataset containing more than 2000 words performed by over 100 signers
- The dataset will be made publicly available to the research community
- It is the largest public ASL dataset to facilitate word-level sign recognition research
- The researchers used the dataset to experiment with several deep learning methods for word-level sign recognition and evaluate their performance on a large scale
- Two different models were implemented and compared, one based on visual appearance and the other based on 2D human pose
- A novel pose-based temporal graph convolutional network (Pose-TGCN) was proposed which models spatial and temporal dependencies in human pose trajectories simultaneously and improved the performance of the pose-based method
- The results showed that the pose-based and appearance-based models achieved comparable performances up to 62.63% at top-10 accuracy on 2000 words

- For TGCN:
  - TGCN improves classification accuracy compared to Pose-GRU
  - TGCN captures both spatial and temporal relationships of the body keypoints
  - TGCN achieved comparable results with I3D in terms of top-5 and top-10 accuracy on the WLASL2000 dataset
  - TGCN effectively encodes human motion information
  - Training the TGCN model in an end-to-end fashion could further improve recognition performance

- For I3D:
  - I3D performed better than VGG-GRU
  - I3D has larger network capacity and is pretrained on multiple datasets
  - I3D achieved comparable results with TGCN in terms of top-5 and top-10 accuracy on the WLASL2000 dataset
  - I3D is trained in an end-to-end fashion which reduces errors in spatial features
