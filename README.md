# 314511067 Exercise 2.4: 基於 GAN 的 MIMO 通道建模與生成

本練習展示如何利用 **QuaDRiGa (QUAsi Deterministic RadIo channel GeneraTor)** 產生真實的無線通道數據，並進一步使用 **Conditional GAN (CGAN)** 框架來學習並模擬這些通道的物理特性。

## 專案概述
在現代無線通訊中，精確的通道模型對於系統設計至關重要。本程式分為兩個主要階段：
* **階段 A：物理數據採集**：使用 QuaDRiGa 模擬器，根據 3GPP 標準產生特定場景（如室內辦公室、城市環境）下的 MIMO 通道矩陣 $H$。
* **階段 B：生成式模型訓練**：使用深度學習中的 CGAN 訓練一個生成器（Generator），使其能根據發送的符號標籤與通道狀態，產生與真實接收訊號 $y = hx + n$ 統計特性一致的樣本。



---

## 執行流程

1.  **數據準備**：執行 MATLAB 腳本，透過 QuaDRiGa 產出通道數據集 `h_dataset`。
2.  **模型訓練**：
    * 運行訓練腳本，將 `h_dataset` 餵入 Python 程式。
    * 觀察生成器與判別器的 Loss 曲線，確保兩者達到競爭平衡。
3.  **驗證與評估**：
    * 比較 GAN 產出的訊號分佈與真實物理模擬的訊號分佈。

---

## 環境需求
* **MATLAB**: 用於執行 QuaDRiGa 工具箱。
* **Python 3.x**: 使用 TensorFlow 框架。
* **核心套件**: `numpy`, `matplotlib`, `scipy`, `tensorflow`。

---
