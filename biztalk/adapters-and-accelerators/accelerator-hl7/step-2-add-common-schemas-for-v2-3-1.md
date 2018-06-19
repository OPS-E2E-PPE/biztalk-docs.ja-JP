---
title: '手順 2: v2.3.1 の一般的なスキーマを追加する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba84c9f45c477aefe7615eca906c40014b06bd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206514"
---
# <a name="step-2-add-common-schemas-for-v231"></a>手順 2: v2.3.1 の一般的なスキーマを追加します。
この手順では、BTAHL7231Common プロジェクト テンプレートに基づく新しいプロジェクトを作成します。 このテンプレートに含まれます (データ型、セグメント、およびテーブルの値) の 3 つの一般的なスキーマを[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) v2.3.1 メッセージ インスタンスの検証に使用します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これらの共通スキーマを使用して、個々 のメッセージの受信のバッチで使用するスキーマを含め、HL7 v2.3.1 スキーマと共に (ADT ^ A03)。  
  
 ステップの最後に、アセンブリに厳密なキーを割り当てるし、展開します。 2 番目の強力なキー; を作成する必要はありません。作成した厳密なキーを使用する[手順 1: ヘッダーの追加および確認スキーマ](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)です。  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a>V2.3.1 一般的なスキーマを追加してアセンブリを展開するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。  
  
3.  **テンプレート**セクションで、 **BTAHL7V231Common プロジェクト**です。  
  
4.  **名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。  
  
5.  **ソリューション**ボックスで、**ソリューションに追加**です。  
  
6.  **[OK]** をクリックします。  
  
    > [!NOTE]
    >  ソリューション エクスプ ローラーで、3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) は、プロジェクトに含まれます。  
  
7.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Common プロジェクト**、クリックして**プロパティ**です。  
  
8.  BTAHL7V231Common プロパティ ページ ダイアログ ボックスで、をクリックして**署名**です。  
  
9. 確認**アセンブリに署名**チェック ボックスをオンします。  
  
10. 厳密な名前キー ファイルの選択 でドロップダウン リストを選択します。  
  
11. 参照 **: \Batching チュートリアル** **key.snk**、順にクリック**開く**です。  
  
12. 右クリック**BTAHL7V231Common**、クリックして**展開**です。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。  
  
 進みます[手順 3: トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)です。