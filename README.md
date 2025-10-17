# TensorFlow.js Machine Learning Playground

Interactive web-based machine learning demos showcasing linear regression and binary classification using TensorFlow.js. Built with Materialize CSS framework for a clean, modern interface.

## Features

- **Linear Regression Demo**: Predicts house prices using the King County housing dataset
- **Binary Classification Demo**: COVID-19 case prediction using US counties data
- **Real-time Visualization**: Interactive plots using TensorFlow Vis
- **In-Browser Training**: All ML models train directly in the browser using TensorFlow.js
- **Modern UI**: Clean interface built with Materialize CSS

## Tech Stack

- **Framework**: TensorFlow.js 2.0+
- **Visualization**: TensorFlow Vis for interactive charts
- **Frontend**: HTML5, Vanilla JavaScript
- **Styling**: Materialize CSS, Bootstrap
- **Server**: HTTP-server for local development

## Installation

### Prerequisites
- Node.js 14+ and npm

### Setup

1. Clone the repository:
```bash
git clone https://github.com/CodeBalch25/Machine-Learning-Tensorflow.js.git
cd Machine-Learning-Tensorflow.js
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm start
```

4. Open your browser and navigate to:
   - Linear Regression: `http://localhost:8080/linearregression.html`
   - Binary Classification: `http://localhost:8080/binaryclassification.html`

## Project Structure

```
Machine-Learning-Tensorflow.js/
├── linearregression.html       # House price prediction demo
├── binaryclassification.html   # COVID-19 case classification
├── kc_house_data.csv          # King County housing dataset
├── us-counties.csv            # US counties COVID data
├── package.json               # Node dependencies
└── README.md                  # Documentation
```

## Demos

### 1. Linear Regression - House Price Prediction

**Dataset**: King County Housing Data
- Features: Square footage, bedrooms, bathrooms, year built, etc.
- Target: House sale prices
- Techniques: Feature normalization, gradient descent optimization

**Key Features:**
- Interactive scatter plots showing prediction accuracy
- Real-time training loss visualization
- Multiple feature exploration
- Model performance metrics

### 2. Binary Classification - COVID-19 Prediction

**Dataset**: US Counties Data
- Features: Population, demographics, geographic data
- Target: Binary classification (High/Low risk)
- Techniques: Logistic regression, sigmoid activation

**Key Features:**
- Decision boundary visualization
- Confusion matrix display
- Precision and recall metrics
- ROC curve analysis

## How It Works

### Linear Regression Pipeline:
1. Load and normalize housing data
2. Create TensorFlow.js sequential model
3. Define loss function (Mean Squared Error)
4. Train using Adam optimizer
5. Visualize predictions vs actual values
6. Evaluate model performance

### Classification Pipeline:
1. Load and preprocess county data
2. Build neural network with sigmoid output
3. Binary cross-entropy loss function
4. Train with mini-batch gradient descent
5. Plot decision boundaries
6. Calculate accuracy and F1 score

## Code Examples

### Creating a Linear Regression Model:
```javascript
const model = tf.sequential();
model.add(tf.layers.dense({
    inputShape: [1],
    units: 1
}));

model.compile({
    optimizer: tf.train.adam(),
    loss: 'meanSquaredError'
});
```

### Training the Model:
```javascript
await model.fit(trainX, trainY, {
    epochs: 100,
    callbacks: {
        onEpochEnd: (epoch, logs) => {
            console.log(`Epoch ${epoch}: loss = ${logs.loss}`);
        }
    }
});
```

## Dependencies

```json
{
    "@tensorflow/tfjs": "^2.0.1",
    "@tensorflow/tfjs-node": "^2.0.1",
    "@tensorflow/tfjs-vis": "latest",
    "http-server": "^0.12.3"
}
```

## Performance

- **Training Speed**: Optimized for browser execution using WebGL
- **Model Size**: Lightweight models (~100KB)
- **Inference Time**: Real-time predictions (<10ms)
- **Browser Support**: Chrome, Firefox, Safari, Edge (modern versions)

## Datasets

### King County Housing Dataset
- Records: 21,000+ home sales
- Features: 19 numerical and categorical variables
- Time Period: 2014-2015
- Source: Public county records

### US Counties COVID Dataset
- Records: 3,000+ US counties
- Features: Population, cases, deaths, geographic data
- Updated: Real-time (dependent on source)

## Future Enhancements

- [ ] Add CNN for image classification
- [ ] Implement transfer learning demos
- [ ] Add NLP sentiment analysis example
- [ ] Mobile-responsive design improvements
- [ ] Save/load trained models
- [ ] Add more datasets and examples

## Learning Resources

This project demonstrates:
- TensorFlow.js fundamentals
- Model training in the browser
- Data preprocessing techniques
- Visualization best practices
- Gradient descent optimization
- Evaluation metrics

## Browser Compatibility

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## License

This project is open source and available under the MIT License.

## Author

**Timothy Balch** - [@CodeBalch25](https://github.com/CodeBalch25)

## Acknowledgments

- TensorFlow.js team for the amazing framework
- Materialize CSS for the UI components
- Google Developers for TensorFlow Vis

## Tags

`tensorflow-js` `machine-learning` `web-ml` `javascript` `linear-regression` `classification` `data-science` `browser-ml` `interactive-visualization`
