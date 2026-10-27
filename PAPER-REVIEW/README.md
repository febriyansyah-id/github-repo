## Statistik Koleksi

| Kategori | Jumlah |
| --- | ---: |
| Vision Transformer (ViT) untuk Klasifikasi Malware | 9 |
| Vision Mamba (ViM) | 7 |
| Paper yang Membahas ViT dan ViM | 2 |
| Natural Language Processing (NLP) | 11 |
| Klasifikasi Malware Berbasis Citra | 21 |
| Deteksi Malware di Luar Klasifikasi Citra | 3 |
| Survei, Explainability, dan Kualitas Dataset | 8 |
| Total paper | **61** |
| Rentang tahun | **2023-2026** |

## Kategori Paper

### Vision Transformer (ViT) untuk Klasifikasi Malware

Paper yang secara eksplisit menggunakan arsitektur Vision Transformer untuk klasifikasi malware berbasis citra. Koleksi saat ini belum memuat paper arsitektur ViT umum di luar domain malware.

| Tahun | Paper | Fokus utama |
| --- | --- | --- |
| 2023 | [Enhancing Malware Classification with Vision Transformers: A Comparative Study with Traditional CNN Models](2023%20-%20Enhancing%20Malware%20Classification%20with%20Vision%20Transformers%20A%20Comparative%20Study%20with%20Traditional%20CNN%20Models/README.md) | ViT, CNN, Malimg malware images |
| 2023 | [ViT4Mal: Lightweight Vision Transformer for Malware Detection on Edge Devices](2023%20-%20ViT4Mal%20Lightweight%20Vision%20Transformer%20for%20Malware%20Detection%20on%20Edge%20Devices/README.md) | Lightweight ViT, malware images, IoT/FPGA |
| 2024 | [Accelerating Malware Classification: A Vision Transformer Solution](2024%20-%20Accelerating%20Malware%20Classification%20A%20Vision%20Transformer%20Solution/README.md) | LeViT-MC, MaleVis RGB, CNNâ€“ViT dua tahap |
| 2024 | [Convolutional-free Malware Image Classification using Self-attention Mechanisms](2024%20-%20Convolutional-free%20Malware%20Image%20Classification%20using%20Self-attention%20Mechanisms/README.md) | RGB malware images, GAN oversampling, Vision Transformer self-attention |
| 2024 | [Data-Efficient Image Transformers for Robust Malware Family Classification](2024%20-%20Data-Efficient%20Image%20Transformers%20for%20Robust%20Malware%20Family%20Classification/README.md) | DeiT, HGBO, citra RGB MaleVis dan MalNet-Image Tiny |
| 2024 | [Vision Based Malware Classification Using Deep Neural Network with Hybrid Data Augmentation](2024%20-%20Vision%20Based%20Malware%20Classification%20Using%20Deep%20Neural%20Network%20with%20Hybrid%20Data%20Augmentation/README.md) | Malimg, Vision Transformer, DCGAN and hybrid augmentation |
| 2025 | [Image-Based Malware Multiclass Classification Using Vision Transformer Architecture](2025%20-%20Image-Based%20Malware%20Multiclass%20Classification%20Using%20Vision%20Transformer%20Architecture/README.md) | ViT, Malimg, klasifikasi malware multikelas |
| 2025 | [MalFormer: A Novel Vision Transformer Model for Robust Malware Analysis](2025%20-%20MalFormer%20A%20Novel%20Vision%20Transformer%20Model%20for%20Robust%20Malware%20Analysis/README.md) | Malware ViT, multiscale attention, robustness to obfuscation |
| 2026 | [MSA-ViT: A Multi-Scale Vision Transformer for Robust Malware Image Classification](2026%20-%20MSA-ViT%20A%20Multi-Scale%20Vision%20Transformer%20for%20Robust%20Malware%20Image%20Classification/README.md) | Multi-scale ViT, MaleVis, robustness |

### Vision Mamba (ViM)

Paper yang berfokus pada Vision Mamba atau visual state-space models, termasuk penerapan Mamba untuk klasifikasi citra malware.

| Tahun | Paper | Fokus utama |
| --- | --- | --- |
| 2024 | [A Survey on Visual Mamba](2024%20-%20A%20Survey%20on%20Visual%20Mamba/README.md) | Survey, visual SSM taxonomy and applications |
| 2024 | [GroupMamba: Efficient Group-Based Visual State Space Model](2024%20-%20GroupMamba%20Efficient%20Group-Based%20Visual%20State%20Space%20Model/README.md) | Group SSM, multi-direction scan, ImageNet/COCO/ADE20K |
| 2024 | [Malware Image Classification Based on Mamba](2024%20-%20Malware%20Image%20Classification%20Based%20on%20Mamba/README.md) | Mamba, state-space model, MalImg |
| 2024 | [Vision Mamba: Efficient Visual Representation Learning with Bidirectional State Space Model](2024%20-%20Vision%20Mamba%20Efficient%20Visual%20Representation%20Learning%20with%20Bidirectional%20State%20Space%20Model/README.md) | Bidirectional SSM, visual backbone, ImageNet/COCO/ADE20K |
| 2024 | [VSSD: Vision Mamba with Non-Causal State Space Duality](2024%20-%20VSSD%20Vision%20Mamba%20With%20Non-Causal%20State%20Space%20Duality/README.md) | Non-causal SSD, visual SSM, ImageNet/COCO/ADE20K |
| 2025 | [DefMamba: Deformable Visual State Space Model](2025%20-%20DefMamba%20Deformable%20Visual%20State%20Space%20Model/README.md) | Deformable SSM scanning, ImageNet/COCO/ADE20K |
| 2025 | [Mamba-Adaptor: State Space Model Adaptor for Visual Recognition](2025%20-%20Mamba-Adaptor%20State%20Space%20Model%20Adaptor%20for%20Visual%20Recognition/README.md) | SSM adaptor, transfer learning, ImageNet/COCO |

### Paper yang Membahas ViT dan ViM

Paper computer vision yang membahas gabungan atau perbandingan pendekatan Mamba visual dan Transformer/attention.

| Tahun | Paper | Fokus utama |
| --- | --- | --- |
| 2024 | [MambaOut: Do We Really Need Mamba for Vision?](2024%20-%20MambaOut%20Do%20We%20Really%20Need%20Mamba%20for%20Vision/README.md) | SSM ablation, Gated CNN, ImageNet/COCO/ADE20K |
| 2024 | [MambaVision: A Hybrid Mamba-Transformer Vision Backbone](2024%20-%20MambaVision%20A%20Hybrid%20Mamba-Transformer%20Vision%20Backbone/README.md) | Hybrid CNN-Mamba-Transformer, ImageNet/COCO/ADE20K |

### Natural Language Processing (NLP)

Paper tentang model bahasa dan pemrosesan teks.

| Tahun | Paper | Fokus utama |
| --- | --- | --- |
| 2023 | [QLoRA Efficient Finetuning of Quantized LLMs](2023%20-%20QLoRA%20Efficient%20Finetuning%20of%20Quantized%20LLMs/README.md) | Quantization, LoRA, PEFT |
| 2023 | [Self-RAG Learning to Retrieve Generate and Critique Through Self-Reflection](2023%20-%20Self-RAG%20Learning%20to%20Retrieve%20Generate%20and%20Critique%20Through%20Self-Reflection/README.md) | Adaptive RAG, self-reflection |
| 2024 | [Direct Preference Optimization DPO](2024%20-%20Direct%20Preference%20Optimization%20DPO/README.md) | LLM alignment, preference optimization |
| 2024 | [REAR A Relevance-Aware Retrieval-Augmented Framework for Open-Domain Question Answering](2024%20-%20REAR%20A%20Relevance-Aware%20Retrieval-Augmented%20Framework%20for%20Open-Domain%20Question%20Answering/README.md) | RAG, relevance assessment, QA |
| 2025 | [Advancing Few-Shot Named Entity Recognition with Large Language Model](2025%20-%20Advancing%20Few-Shot%20Named%20Entity%20Recognition%20with%20Large%20Language%20Model/README.md) | Few-shot NER, metric learning, LLM |
| 2025 | [Construction and Implementation of Knowledge Enhancement Pre-Trained Language Model for Text Sentiment Analysis](2025%20-%20Construction%20and%20Implementation%20of%20Knowledge%20Enhancement%20Pre-Trained%20Language%20Model%20for%20Text%20Sentiment%20Analysis/README.md) | Sentiment analysis, knowledge enhancement |
| 2025 | [GPT-NER Named Entity Recognition via Large Language Models](2025%20-%20GPT-NER%20Named%20Entity%20Recognition%20via%20Large%20Language%20Models/README.md) | NER, text generation, self-verification |
| 2026 | [aCat Automatically Choosing Anchor Tokens in Prompt for Natural Language Understanding](2026%20-%20aCat%20Automatically%20Choosing%20Anchor%20Tokens%20in%20Prompt%20for%20Natural%20Language%20Understanding/README.md) | Prompt tuning, reinforcement learning |
| 2026 | [Enriching the Low-Resource Neural Machine Translation with Large Language Model](2026%20-%20Enriching%20the%20Low-Resource%20Neural%20Machine%20Translation%20with%20Large%20Language%20Model/README.md) | Machine translation, knowledge distillation |
| 2026 | [Improving Few-Shot Named Entity Recognition for Large Language Models Using Structured Dynamic Prompting with Retrieval Augmented Generation](2026%20-%20Improving%20Few-Shot%20Named%20Entity%20Recognition%20for%20Large%20Language%20Models%20Using%20Structured%20Dynamic%20Prompting%20with%20Retrieval%20Augmented%20Generation/README.md) | Biomedical NER, dynamic prompting, RAG |
| 2026 | [Training-Free Layer Selection for Partial Fine-Tuning of Language Models](2026%20-%20Training-Free%20Layer%20Selection%20for%20Partial%20Fine-Tuning%20of%20Language%20Models/README.md) | Partial fine-tuning, layer selection |

### Klasifikasi Malware Berbasis Citra

Paper klasifikasi malware dari citra yang tidak secara khusus berfokus pada ViT atau ViM.

| Tahun | Paper | Fokus utama |
| --- | --- | --- |
| 2023 | [CNN vs Transformer Variants - Malware Classification Using Binary Malware Images](2023%20-%20CNN%20vs%20Transformer%20Variants%20-%20Malware%20Classification%20Using%20Binary%20Malware%20Images/README.md) | CNN, Transformer, binary malware image |
| 2023 | [Image-Based Malware Detection Using Î±-Cuts and Binary Visualisation](2023%20-%20Image-Based%20Malware%20Detection%20Using%20Alpha-Cuts%20and%20Binary%20Visualisation/README.md) | Î±-cut, binary visualization, ResNet50 |
| 2023 | [Malware Detection Using Image Representation of Malware Data and Transfer Learning](2023%20-%20Malware%20Detection%20Using%20Image%20Representation%20of%20Malware%20Data%20and%20Transfer%20Learning/README.md) | Malimg, VGG16/ResNet-50, stacked ML |
| 2024 | [A Comparative Performance Analysis of Malware Detection Algorithms Based on Various Texture Features and Classifiers](2024%20-%20A%20Comparative%20Performance%20Analysis%20of%20Malware%20Detection%20Algorithms%20Based%20on%20Various%20Texture%20Features%20and%20Classifiers/README.md) | Malimg/MaleVis, texture descriptors, classical classifiers |
| 2024 | [Android Malware Detection Based on RGB Images and Multi-feature Fusion](2024%20-%20Android%20Malware%20Detection%20Based%20on%20RGB%20Images%20and%20Multi-feature%20Fusion/README.md) | Fusi DEX, manifest, API menjadi citra RGB |
| 2024 | [Deep Learning Applied to Imbalanced Malware Datasets Classification](2024%20-%20Deep%20Learning%20Applied%20to%20Imbalanced%20Malware%20Datasets%20Classification/README.md) | MobileNet FT, class imbalance, Malimg/MaleVis/Fusion |
| 2024 | [Deep Multi-Task Learning for Malware Image Classification](2024%20-%20Deep%20Multi-Task%20Learning%20for%20Malware%20Image%20Classification/README.md) | Multi-task learning, citra malware lintas format |
| 2024 | [Efficient and Generalized Image-Based CNN Algorithm for Multi-Class Malware Detection](2024%20-%20Efficient%20and%20Generalized%20Image-Based%20CNN%20Algorithm%20for%20Multi-Class%20Malware%20Detection/README.md) | CNN, multiclass malware detection |
| 2024 | [Enhanced Image-Based Malware Classification Using Transformer-Based Convolutional Neural Networks](2024%20-%20Enhanced%20Image-Based%20Malware%20Classification%20Using%20Transformer-Based%20Convolutional%20Neural%20Networks/README.md) | CNN-Transformer, malware images |
| 2025 | [An Efficient Malware Detection Method Using a Hybrid ResNet-Transformer Network and IGOA-Based Wrapper Feature Selection](2025%20-%20An%20Efficient%20Malware%20Detection%20Method%20Using%20a%20Hybrid%20ResNet-Transformer%20Network%20and%20IGOA-Based%20Wrapper%20Feature%20Selection/README.md) | ResNet, Transformer, feature selection |
| 2025 | [An Explainable Hybrid CNN-Transformer Architecture for Malware Image Classification](2025%20-%20An%20Explainable%20Hybrid%20CNN-Transformer%20Architecture%20for%20Malware%20Image%20Classification/README.md) | Explainable AI, CNN-Transformer |
| 2025 | [CNN-AutoMIC Combining Convolutional Neural Network and Autoencoder to Learn Non-Linear Features for KNN-Based Malware Image Classification](2025%20-%20CNN-AutoMIC%20Combining%20Convolutional%20Neural%20Network%20and%20Autoencoder%20to%20Learn%20Non-Linear%20Features%20for%20KNN-Based%20Malware%20Image%20Classification/README.md) | CNN, autoencoder, KNN |
| 2025 | [Enhancing Malware Detection via RGB Assembly Visualization and Hybrid Deep Learning Models](2025%20-%20Enhancing%20Malware%20Detection%20via%20RGB%20Assembly%20Visualization%20and%20Hybrid%20Deep%20Learning%20Models/README.md) | RGB visualization, EfficientNet, DenseNet |
| 2025 | [Multimodal Malware Classification Using Proposed Ensemble Deep Neural Network Framework](2025%20-%20Multimodal%20Malware%20Classification%20Using%20Proposed%20Ensemble%20Deep%20Neural%20Network%20Framework/README.md) | CNN-LSTM, late fusion, citra malware dan fitur numerik |
| 2025 | [Semantic Lossless Encoded Image Representation for Malware Classification](2025%20-%20Semantic%20Lossless%20Encoded%20Image%20Representation%20for%20Malware%20Classification/README.md) | Encoding bytecode lossless, CNN-SPP, row-patch Transformer |
| 2025 | [Through the Static: Demystifying Malware Visualization via Explainability](2025%20-%20Through%20the%20Static%20Demystifying%20Malware%20Visualization%20via%20Explainability/README.md) | Replicability, GradCAM/HiResCAM, masking untuk ViT |
| 2026 | [AD-CapsFPN An Asymmetric Dilated Convolutional Capsule Network with Feature Pyramid for Malware Classification](2026%20-%20AD-CapsFPN%20An%20Asymmetric%20Dilated%20Convolutional%20Capsule%20Network%20with%20Feature%20Pyramid%20for%20Malware%20Classification/README.md) | Capsule network, feature pyramid |
| 2026 | [Cybersecurity Oriented Malware Classification Using ParaECA-LSTMNet with a Hybrid Attention Guided CNN-LSTM Framework](2026%20-%20Cybersecurity%20Oriented%20Malware%20Classification%20Using%20ParaECA-LSTMNet%20with%20a%20Hybrid%20Attention%20Guided%20CNN-LSTM%20Framework/README.md) | Malimg grayscale, CNN-ECA-LSTM, klasifikasi keluarga |
| 2026 | [Image-Based Malware Classification Using DCGAN-Augmented Data and a CNN-Transformer Hybrid Model](2026%20-%20Image-Based%20Malware%20Classification%20Using%20DCGAN-Augmented%20Data%20and%20a%20CNN-Transformer%20Hybrid%20Model/README.md) | DCGAN, data augmentation, CNN-Transformer |
| 2026 | [MCPDS Image-Based Malware Classification Method Using Dual-Information Encoding and Pooling Depthwise Separable CNN](2026%20-%20MCPDS%20Image-Based%20Malware%20Classification%20Method%20Using%20Dual-Information%20Encoding%20and%20Pooling%20Depthwise%20Separable%20CNN/README.md) | PE metadata, depthwise separable CNN |
| 2026 | [X-MET: Multimodal Entropyâ€“Visual Deep Learning Technique for Strengthening Cyber Governance and Resilient Digital Infrastructure](2026%20-%20X-MET%20Multimodal%20Entropy-Visual%20Deep%20Learning%20Technique%20for%20Strengthening%20Cyber%20Governance%20and%20Resilient%20Digital%20Infrastructure/README.md) | Byteplot grayscale, entropy, fusi multimodal lintas format |

### Deteksi Malware di Luar Klasifikasi Citra

Paper deteksi malware yang fokus utamanya bukan klasifikasi citra malware.

| Tahun | Paper | Fokus utama |
| --- | --- | --- |
| 2023 | [Machine Learning Based Fileless Malware Traffic Classification Using Image Visualization](2023%20-%20Machine%20Learning%20Based%20Fileless%20Malware%20Traffic%20Classification%20Using%20Image%20Visualization/README.md) | Cobalt Strike, visualisasi payload jaringan, CNN |
| 2024 | [Malware Analysis Using Transformer Based Models: An Empirical Study](2024%20-%20Malware%20Analysis%20Using%20Transformer%20Based%20Models%20An%20Empirical%20Study/README.md) | Studi CNN, CNNâ€“Transformer, dan ViT pada Android/IoT |
| 2025 | [OPTISTACK: A Hybrid Ensemble Learning and XAI-Based Approach for Malware Detection in Compressed Files](2025%20-%20OPTISTACK%20A%20Hybrid%20Ensemble%20Learning%20and%20XAI-Based%20Approach%20for%20Malware%20Detection%20in%20Compressed%20Files/README.md) | Entropy, stacking ensemble, XAI, compressed files |

### Survei, Explainability, dan Kualitas Dataset

Paper survei/tinjauan, explainable AI, dan evaluasi mutu dataset visual malware.

| Tahun | Paper | Fokus utama |
| --- | --- | --- |
| 2024 | [A Comprehensive Analysis of Explainable AI for Malware Hunting](2024%20-%20A%20Comprehensive%20Analysis%20of%20Explainable%20AI%20for%20Malware%20Hunting/README.md) | XAI, explainable malware detection, SHAP/LIME/Grad-CAM |
| 2024 | [SoK: Visualization-Based Malware Detection Techniques](2024%20-%20SoK%20Visualization-Based%20Malware%20Detection%20Techniques/README.md) | SoK, malware visualization taxonomy and research challenges |
| 2025 | [A Survey on ML Techniques for Multi-Platform Malware Detection: Securing PC, Mobile Devices, IoT, and Cloud Environments](2025%20-%20A%20Survey%20on%20ML%20Techniques%20for%20Multi-Platform%20Malware%20Detection/README.md) | Multi-platform malware, ML/DL, dataset and feature survey |
| 2025 | [Application of Deep Learning in Malware Detection: A Review](2025%20-%20Application%20of%20Deep%20Learning%20in%20Malware%20Detection%20A%20Review/README.md) | Tinjauan sistematis, citra malware, sekuens, augmentasi |
| 2025 | [Deep Learning Approaches for Malware Detection: A Comprehensive Review of Techniques, Challenges, and Future Directions](2025%20-%20Deep%20Learning%20Approaches%20for%20Malware%20Detection%20A%20Comprehensive%20Review%20of%20Techniques%20Challenges%20and%20Future%20Directions/README.md) | CNN/RNN/hybrid, tinjauan deteksi malware |
| 2025 | [Explainable Artificial Intelligence (XAI) for Malware Analysis: A Survey of Techniques, Applications, and Open Challenges](2025%20-%20Explainable%20Artificial%20Intelligence%20XAI%20for%20Malware%20Analysis%20A%20Survey%20of%20Techniques%20Applications%20and%20Open%20Challenges/README.md) | XAI, SHAP/LIME/Grad-CAM, interpretabilitas malware |
| 2025 | [MalScore: A Quality Assessment Framework for Visual Malware Datasets Using No-Reference Image Quality Metrics](2025%20-%20MalScore%20A%20Quality%20Assessment%20Framework%20for%20Visual%20Malware%20Datasets%20Using%20No-Reference%20Image%20Quality%20Metrics/README.md) | NR-IQA, penilaian dataset malware visual, MaleVis |
| 2025 | [Systematic Review: Malware Detection and Classification in Cybersecurity](2025%20-%20Systematic%20Review%20Malware%20Detection%20and%20Classification%20in%20Cybersecurity/README.md) | SLR, PRISMA, malware detection methods and datasets |

## Format Folder

Setiap paper menggunakan struktur berikut:

```text
PAPER-REVIEW/
|-- README.md
|-- TAHUN - Judul Paper/
    |-- README.md
    |-- IMAGE/
        |-- gambar-metode.png
        |-- hasil-eksperimen.png
```

- `README.md` berisi review paper, dataset, metode, hasil, kelebihan, keterbatasan, dan sumber.
- `IMAGE/` berisi gambar asli atau visual penting yang dirujuk dalam review.
- PDF tidak disimpan di repository; tautan PDF dicantumkan pada review bila tersedia.

## Struktur Review

Review paper disusun dengan urutan:

1. Identitas paper
2. Tujuan penelitian
3. Dataset dan evaluasi
4. Metode atau arsitektur model
5. Domain penelitian
6. Hasil utama
7. Analisis kontribusi model
8. Kelebihan
9. Keterbatasan
10. Kesimpulan review
11. Sumber

## Catatan Kategori

Beberapa metode memiliki keterkaitan lintas bidang. RAG termasuk NLP karena memproses pertanyaan dan dokumen teks, sedangkan klasifikasi malware berbasis citra termasuk Computer Vision yang diterapkan pada domain cybersecurity.

## Menambahkan Paper Baru

1. Buat folder dengan format `TAHUN - Judul Paper`.
2. Tambahkan `README.md` dan folder `IMAGE`.
3. Masukkan gambar relevan dan rujuk di README paper.
4. Tambahkan paper ke kategori yang sesuai pada README utama.
5. Cantumkan sumber publikasi dan tautan yang dapat diverifikasi.
