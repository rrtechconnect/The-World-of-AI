

**Deep Learning with PyTorch : Siamese Network**

Which of the following is/are the applications of siamese network ? 

    Person Re-Identification
    Facial Recognition 
    Signature Matching 

which cost function was in order to train siamese network ? 

    nn.TripletMarginLoss()


How to compare query image embeddings with embeddings stored in the database ? 

    distance formula like euclidean distance 


A = io.imread(DATA_DIR+ i)

A = torch.from_numpy(A).permute(2, 0, 1) / 255.0

A = A.to(DEVICE)

A_enc = model(A.unsqueeze(0))

Here .unsqueeze(0) will add an extra dimension at axis 0 which will represent as batch size 1.
