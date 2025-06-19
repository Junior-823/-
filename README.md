# 垃圾桶溢出偵測系統 | Garbage Overflow Detector (Haar Cascade Classifier)

📘 本專案為元智大學《電機導論：電腦視覺與影像處理課程》的期末專題，目的是透過 OpenCV 的 Haar cascade 技術來實作一個能夠自動辨識「垃圾桶溢出」情況的系統。

---

## 🎯 專題目標
- 偵測校園中垃圾桶是否有垃圾溢出的情況
- 利用自己拍攝與標註的資料來訓練 Haar cascade 分類器
- 實作可以用圖片或即時攝影機進行辨識的應用程式

---

## 📁 專案結構

---



## 🚀 專案流程說明

1. **拍攝與標註**：使用手機拍攝垃圾桶圖片 → 用 `labelImg` 標註 → 產出 Pascal VOC XML。
2. **預處理**：
   - 使用 `prepare_dataset.py` 將 XML 轉為 `positives.txt`
   - 用 `resize_images.py` 將正樣本轉為 24x24
   - 使用 `import_glob.py` 製作 `negatives.txt`
3. **建立樣本與訓練**：
   - 使用 `create_samples.py` 建立 `positives.vec`
   - 使用 `opencv_traincascade.exe` 進行多階段訓練
4. **模型測試**：
   - 使用 `test_detector.py` 測試單張圖片
   - 或 `batch_test_detector1.py` 測試整批圖片
   - 偵測結果儲存於 `detections/`、`detections_full/` 中



