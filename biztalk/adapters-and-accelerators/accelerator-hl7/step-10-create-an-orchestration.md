---
title: 手順 10:オーケストレーションを作成する |Microsoft Docs
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
ms.openlocfilehash: da424576feb01762b703f43e796956e2dbb25228
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288994"
---
# <a name="step-10-create-an-orchestration"></a>手順 10:オーケストレーションを作成します。
この手順では、患者、ADT_A04 メッセージは完全に表示される追加の詳細を取得するためのビジネス プロセスを表すオーケストレーションを作成するのにオーケストレーション デザイナーを使用します。 オーケストレーション デザイナーを使用して、このビジネス プロセスのアクションを表すために必要なオーケストレーション図形を選択します。 以降の演習では、正しく動作させるように図形を構成する追加の情報を提供します。  
  
> [!NOTE]
>  次の手順で作成されたオーケストレーションは、このチュートリアルのコンテキストでのみ機能します。 オーケストレーションが正しく機能するためには、アセンブリ参照、マップ、および他の中に、このチュートリアルを使用して作成したアーティファクトが必要です。  
  
### <a name="to-create-an-orchestration"></a>オーケストレーションを作成するには  
  
1. ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2. **新しい項目の追加** ダイアログ ボックスで、**カテゴリ**ウィンドウで、をクリックして**オーケストレーション ファイル**します。  
  
3. **テンプレート**ウィンドウで、をクリックして**BizTalk オーケストレーション**します。  
  
4. **名前**フィールドに「**ドアベル Orchestration.odx** (、単語の間にスペースがあることに注意してください**ドアベル**と**オーケストレーション**。) クリックし、オーケストレーションの名前**追加**新しいオーケストレーション ファイルを作成します。  
  
5. **ビュー**  メニューのをクリックして**ツールボックス**します。  
  
6. **ツールボックス**ウィンドウで、ドラッグ、**受信**図形をデザイン ビュー サーフェイスにし、ラベルが付いた領域にドロップ**ここで、ツールボックスから図形をドロップ**します。  
  
7. (画面の右下) で [プロパティ] ウィンドウで、**名前**プロパティと型**DoorbellReceive**の名前として、**受信**図形し、キーを押します**入力**します。  
  
8. [プロパティ] ウィンドウで次のように変更します。、 **Activate**プロパティを**True**します。  
  
9. ドラッグ、**変換**図形をツールボックスから、下に直接ドロップ、 **DoorbellReceive**図形。  
  
10. (画面の右下) で [プロパティ] ウィンドウで、**名前**プロパティの名前を変更する、**変換**図形を**DoorbellTransform**、し、キーを押します。**入力**します。  
  
11. **ツールボックス**ウィンドウで、ドラッグ、**メッセージの割り当て**図形をデザイン ビュー サーフェイスにし、直接の下の領域にドロップ、 **ConstructMessage_1**図形。  
  
12. オーケストレーションのデザイン ビュー画面でをクリックして、 **[messageassignment_1]** 図形、し、**プロパティ**ウィンドウで、をクリックして**名前**新しい名前を入力**DoorbellFinalTransform**、キーを押しますと**Enter**します。  
  
13. ドラッグ、**送信**図形をツールボックスから、区分線のすぐ下にドロップし、 **DoorbellFinalTransform**図形。  
  
14. (画面の右下) で [プロパティ] ウィンドウで、**名前**プロパティの名前を変更する、**送信**図形を**DoorbellSend**とを押します**入力**します。  
  
    続行する[手順 11。オーケストレーション変数の作成](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)