# Image_Captioning
Image Captioning using VGG16 and LSTM with Deep Learning and NLP.

🖼️ Image Captioning Using VGG16 and LSTM

A Deep Learning-based Image Captioning project that combines Computer Vision and Natural Language Processing to automatically generate descriptive captions for images.

The project uses a pre-trained VGG16 Convolutional Neural Network (CNN) to extract meaningful visual features from images and an LSTM (Long Short-Term Memory) network to generate natural-language captions based on those visual features.

🚀 Project Overview

Image captioning is a multimodal AI task that connects computer vision with natural language processing.

The system takes an image as input and generates a textual description representing the content of that image.

                    Input Image
                         │
                         ▼
                  Pre-trained VGG16
                         │
                         ▼
                Image Feature Extraction
                         │
                         ▼
                  Feature Vector
                         │
                         ▼
                    LSTM Network
                         │
                         ▼
              Word-by-Word Prediction
                         │
                         ▼
                  Generated Caption

✨ Features

- 🖼️ Image-based caption generation
- 🧠 Deep Learning-based architecture
- 👁️ VGG16 for visual feature extraction
- 📝 LSTM for natural-language caption generation
- 🔤 Text preprocessing and tokenization
- 🔢 Caption sequence generation
- 🔗 CNN + RNN integration
- 📚 Uses image-caption training data
- 🤖 Automated image-to-text generation

🛠️ Technologies Used

Technology| Purpose
Python| Core programming language
TensorFlow| Deep Learning framework
Keras| Neural network implementation
VGG16| Image feature extraction
LSTM| Caption generation
NumPy| Numerical computation
Pandas| Data processing
NLTK| Text preprocessing
Matplotlib| Visualization
Pillow| Image processing

🧠 Model Architecture

The project follows an Encoder-Decoder architecture.

Encoder — VGG16

A pre-trained VGG16 network is used as the image encoder.

Instead of training an entire CNN from scratch, the pre-trained network is used to extract visual representations from input images.

Image
  ↓
VGG16
  ↓
Convolutional Feature Extraction
  ↓
Visual Feature Representation

Decoder — LSTM

The extracted image features are combined with caption information and passed to an LSTM-based decoder.

The LSTM generates the caption one word at a time.

Image Features
      +
Previous Words
      ↓
     LSTM
      ↓
Next Word
      ↓
Next Word
      ↓
     ...
      ↓
Complete Caption

🔄 Project Workflow

Dataset
   ↓
Load Images and Captions
   ↓
Clean Caption Text
   ↓
Add Start/End Tokens
   ↓
Tokenization
   ↓
VGG16 Feature Extraction
   ↓
Prepare Image-Text Sequences
   ↓
Train LSTM Caption Generator
   ↓
Generate Caption
   ↓
Evaluate / Test on Image

📚 Dataset

The model requires an image-caption dataset containing images paired with textual descriptions.

A commonly used dataset for this type of project is Flickr8k, which contains thousands of images with multiple human-written captions per image.

The dataset should be downloaded separately and placed in the appropriate local directory.

«Large datasets should generally not be uploaded directly to GitHub because of repository size limitations.»

📝 Text Preprocessing

Before training the caption-generation model, captions are processed to make them suitable for the neural network.

Typical preprocessing includes:

- Converting text to lowercase
- Removing unnecessary characters
- Cleaning punctuation
- Tokenizing captions
- Adding start-of-sequence tokens
- Adding end-of-sequence tokens
- Converting words into numerical sequences
- Padding sequences where necessary

Example:

Original:
"A dog is running through the grass."

Processed:
"startseq a dog is running through the grass endseq"

🔤 Tokenization

The cleaned captions are converted into numerical sequences using a tokenizer.

For example:

startseq → 1
dog      → 25
running  → 63
grass    → 91
endseq   → 2

These sequences are used as input to the LSTM during training.

👁️ VGG16 Feature Extraction

The project uses a pre-trained VGG16 model as the visual feature extractor.

The CNN learns visual representations such as:

- Objects
- Shapes
- Colors
- Textures
- Spatial patterns

The resulting image representation is then passed to the caption-generation component.

🧠 LSTM Caption Generation

The LSTM decoder learns relationships between image features and words.

During training, the model learns to predict the next word based on:

Image Features + Previous Words

For example:

startseq
     ↓
a
     ↓
dog
     ↓
is
     ↓
running
     ↓
outside
     ↓
endseq

This allows the model to generate complete captions rather than simply classifying an image.

📊 Training

The model is trained using image-caption pairs.

During training:

1. Image features are extracted using VGG16.
2. Captions are tokenized.
3. Caption sequences are created.
4. Image features and partial caption sequences are provided to the model.
5. The LSTM learns to predict the next word.
6. Training continues across multiple epochs.

🧪 Testing

After training, a new image can be provided to the model.

The model extracts visual features from the image and generates a caption sequentially until the end-of-sequence token is predicted.

New Image
   ↓
VGG16 Feature Extraction
   ↓
LSTM Decoder
   ↓
Word Prediction
   ↓
Caption

📂 Project Structure

Image-Captioning/
│
├── vgg16-LSTM.ipynb
├── README.md
├── requirements.txt
├── .gitignore
│
└── dataset/
    ├── images/
    └── captions/

The exact dataset/model files may vary depending on the environment used to run the notebook.

⚙️ Installation

1. Clone the Repository

git clone https://github.com/harshithadivvela/Image-Captioning.git
cd Image-Captioning

2. Install Dependencies

pip install -r requirements.txt

3. Open the Notebook

Launch Jupyter Notebook:

jupyter notebook

Then open:

vgg16-LSTM.ipynb

Alternatively, the notebook can be opened and executed using Google Colab.

▶️ Running the Project

Run the notebook cells sequentially.

The general process is:

1. Load dataset
2. Preprocess captions
3. Extract image features using VGG16
4. Prepare tokenized sequences
5. Build the LSTM model
6. Train the model
7. Generate captions
8. Test on unseen images

🎯 Applications

Image captioning can be used in:

- ♿ Accessibility applications
- 🖼️ Automatic image descriptions
- 🔎 Image search systems
- 📱 Social media platforms
- 📰 Media and content management
- 🤖 AI-powered visual assistants
- 📚 Educational applications

🎓 Learning Outcomes

This project provides practical experience with:

- Computer Vision
- Natural Language Processing
- Deep Learning
- Transfer Learning
- CNN architectures
- VGG16
- LSTM networks
- Sequence modeling
- Text tokenization
- Image feature extraction
- Encoder-decoder architectures
- Multimodal AI

🔮 Future Improvements

Possible improvements include:

- Replace VGG16 with more modern CNN architectures
- Use EfficientNet or ResNet for feature extraction
- Add an attention mechanism
- Use Transformer-based caption generation
- Implement Beam Search
- Improve caption quality using pretrained language models
- Add BLEU, METEOR, ROUGE or CIDEr evaluation
- Build a Streamlit interface
- Deploy the model as a web application
- Support real-time image captioning

⚠️ Limitations

- Caption quality depends heavily on the training dataset.
- Generated captions may not always accurately describe an image.
- Training deep learning models can require significant computational resources.
- VGG16 is computationally heavier than many modern lightweight architectures.
- The model may generate grammatically correct but semantically imperfect captions.
- Performance depends on the similarity between training and testing images.

👩‍💻 Author

NagaVenkataLakshmi HamsaVarshitha Divvela

B.Tech – Computer Science & Engineering (AI & ML)

RVR & JC College of Engineering

2025 Graduate

⭐ Acknowledgement

This project demonstrates the application of deep learning techniques to the image captioning problem by combining visual feature extraction with sequence-based language generation.

📌 Disclaimer

This project is developed for educational and portfolio purposes to demonstrate concepts in Computer Vision, Natural Language Processing, and Deep Learning.
