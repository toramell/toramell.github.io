---
title: "Hierarchical Control System for Drones using VLA Models"
excerpt: "VLAモデルによる高レベル意思決定と、MPPIによる低レベル制御を統合した階層型アーキテクチャの実装プロジェクト。<br/><img src='/images/drone-project-teaser.jpg'>"
collection: portfolio
---

## プロジェクト概要
本プロジェクトでは、視覚・言語情報を直接行動に変換する **Vision-Language-Action (VLA) モデル** をドローンのナビゲーションに適用し、未知の動的環境下での自律航行を実現するシステムを開発しています。



## 技術スタックとアーキテクチャ
本システムは、推論コストとリアルタイム性のバランスを取るため、以下の階層型構成を採用しています。

1.  **High-level (VLM/VLA):** * **Google Gemini API / Qwen3.5:** 周囲の状況（画像）と言語指示から、セマンティックな経路計画を生成。
    * **環境:** Ubuntu 22.04 (6000ada) 上で Docker コンテナを用いた開発環境を構築。
2.  **Low-level (Control Theory):**
    * **MPPI (Model Predictive Path Integral):** 高精度な軌道追従と、局所的な動的障害物の回避。
    * **PX4 / Gazebo:** ドローンのフライトコントローラとの連携および物理シミュレーション。

## 実装のポイント
* **高速推論の実現:** VLAモデルの推論遅延を最小化するパイプラインを構築。
* **ロバスト性:** 学部での「通信遅延を考慮した強化学習」の知見を活かし、ネットワーク越しでの遠隔制御における安定性を確保。

