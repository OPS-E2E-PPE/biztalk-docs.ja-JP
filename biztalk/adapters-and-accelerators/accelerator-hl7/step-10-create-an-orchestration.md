---
title: '手順 10: オーケストレーションを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, creating
- creating, orchestrations
- message enrichment tutorial, orchestrations
ms.assetid: 10f5cf3d-4a34-4c80-89d1-c390552cfc09
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc554a6f3c94a077b34ae79a36b8e484eadcd5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206570"
---
# <a name="step-10-create-an-orchestration"></a>手順 10: オーケストレーションを作成します。
このステップでは、患者 ADT_A04 メッセージを完全に作成される追加の詳細を取得するためのビジネス プロセスを表すオーケストレーションを作成するのにオーケストレーション デザイナーを使用します。 オーケストレーション デザイナーを使用して、このビジネス プロセスのアクションを表すために必要なオーケストレーション図形を選択します。 以降の演習では、それらが正しく機能できるように、図形を構成する追加の情報を提供します。  
  
> [!NOTE]
>  次の手順で作成されたオーケストレーションは、このチュートリアルのコンテキストでのみ機能します。 オーケストレーションが正しく機能するためには、アセンブリ参照、マップ、およびその他の成果物をこのチュートリアルを使用しているときに作成する必要があります。  
  
### <a name="to-create-an-orchestration"></a>オーケストレーションを作成するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、クリックして**新しい項目の**します。  
  
2.  **新しい項目の追加** ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**オーケストレーション ファイル**です。  
  
3.  **テンプレート** ウィンドウで、をクリックして**BizTalk オーケストレーション**です。  
  
4.  **名前**フィールドに「**ドアベル Orchestration.odx** (、単語の間にスペースがあることに注意してください**ドアベル**と**オーケストレーション**) をクリックし、オーケストレーションの名前として**追加**新しいオーケストレーション ファイルを作成します。  
  
5.  **ビュー**  メニューのをクリックして**ツールボックス**です。  
  
6.  **ツールボックス** ウィンドウで、ドラッグ、**受信**図形をデザイン ビュー画面にし、ラベルが付いた領域にドロップ**ツールボックスからここに図形をドロップ**です。  
  
7.  (上、画面の右下) の [プロパティ] ウィンドウでをクリックして、**名前**プロパティと型**DoorbellReceive**の名前として、**受信**図形、およびキーを押します**入力**です。  
  
8.  [プロパティ] ウィンドウで変更、 **Activate**プロパティを**True**です。  
  
9. ドラッグ、**変換**図形をツールボックスから、直接の下にドロップして、 **DoorbellReceive**図形です。  
  
10. (上、画面の右下) の [プロパティ] ウィンドウでをクリックして、**名前**の名前を変更するプロパティ、**変換**図形を**DoorbellTransform**、キーを押します**入力**です。  
  
11. **ツールボックス** ウィンドウで、ドラッグ、**メッセージの割り当て**図形をデザイン ビュー画面にし、領域のすぐ下にドロップ、 **ConstructMessage_1**図形です。  
  
12. オーケストレーションのデザイン ビュー サーフェイスでをクリックして、 **MessageAssignment_1**図形、し、[、**プロパティ**] ウィンドウで、をクリックして**名前**新しい名前を入力し、 **DoorbellFinalTransform**、キーを押します**Enter**です。  
  
13. ドラッグ、**送信**図形をツールボックスから、直接の下の区分線にドロップ、 **DoorbellFinalTransform**図形です。  
  
14. (上、画面の右下) の [プロパティ] ウィンドウでをクリックして、**名前**の名前を変更するプロパティ、**送信**図形を**DoorbellSend**、キーを押します**入力**です。  
  
 進みます[手順 11: オーケストレーション変数を作成する](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)