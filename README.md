# 🛒 Grocery Product Recommender

A Gradio-powered Hugging Face Space that recommends similar grocery products based on ingredients using semantic similarity and FAISS search. Optionally displays product images (if available).

[![View on Hugging Face Spaces](https://img.shields.io/badge/🤗%20View%20Space-Hugging%20Face-blueviolet)]((https://huggingface.co/spaces/Maithil06/GroceryRecommendationSystem/))

---

## 🚀 Features

- 🔎 **Semantic Search**: Uses `sentence-transformers` to embed product descriptions
- ⚡ **Fast Recommendations**: Powered by `FAISS` for nearest-neighbor search
- 🧠 **Fuzzy Matching**: Accepts imperfect product names using `difflib`
- 🖼️ **(Optional) Image Display**: Shows product images using HTTPS proxy or local fallback
- 🎨 **Gradio UI**: Clean, interactive UI with dynamic HTML output

---

## 🏗️ Project Structure

```
grocery-product-recommender/
│
├── app.py # Main Gradio app
├── requirements.txt # Python dependencies
├── grocery_metadata_with_images.csv # Product metadata (brand, title, ingredients, code)
├── grocery_embeddings.npy # Precomputed sentence embeddings
└── files/ # (Optional) Local images if S3-hosted ones fail
```

## 📦 Dependencies

Install required packages:

```bash
pip install -r requirements.txt
```
OR

```bash
pip install gradio pandas numpy faiss-cpu sentence-transformers
```
# 📂 Data Files
```grocery_metadata.csv```: Includes product brand, name, ingredients, and barcode (code)

```grocery_embeddings.npy```: 384-dimensional sentence embeddings of ingredient text (using all-MiniLM-L6-v2)

```files/```: Folder for optional pre-downloaded product images (named as <code>.jpg)

# 🧪 Example Inputs

- Alpro Almond Milk
- Kellogg's Corn Flakes
- Heinz Tomato Ketchup
- Oatly Oat Drink

# 🔐 Notes

- Hugging Face Spaces may block images from Open Food Facts S3 due to CORS or HTTPS constraints.
- You can use ```https://images.weserv.nl``` as an HTTPS proxy, or download and serve images locally via file/ paths in your Space.
- For large datasets (>50MB), use Git LFS.

# 🤝 Acknowledgements

- Open Food Facts for the open dataset
- Hugging Face for Gradio and Spaces
- FAISS for similarity search
- Weserv Image Proxy for CORS-compliant image loading
