---
title: "手順 2: V2.3.1 用の共通のスキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, common schemas
- common schemas
ms.assetid: db1a2206-559f-475a-803d-55522cce007e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f8ed36b4a1ae8553e8df488e8fd5a606c0eabd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-create-common-schemas-for-v231"></a>手順 2: V2.3.1 の一般的なスキーマを作成します。
V2.3.1 スキーマは、頻繁に参照されるスキーマは、メッセージ インスタンスの検証に使用します。  
  
### <a name="to-create-a-common-schema-for-v231"></a>V2.3.1 の共通のスキーマを作成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。  
  
3.  テンプレート セクションで、 **BTAHL7V231Common プロジェクト**です。  
  
4.  **名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。  
  
5.  **ソリューション**ボックスで、**ソリューションに追加**です。  
  
6.  **[OK]**をクリックします。  
  
    > [!NOTE]
    >  ソリューション エクスプ ローラーで、3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) は、プロジェクトに含まれます。  
  
7.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Common プロジェクト**、クリックして**プロパティ**です。  
  
8.  BTAHL7V231Common プロパティ ページで、をクリックして**署名**です。  
  
9. 選択、**アセンブリに署名**チェック ボックスをオンします。  
  
10. **厳密な名前キー ファイルを選択して** **\<を参照しています.\>** .  
  
11. 参照\<ドライブ\>: \Batching チュートリアルでは、選択**key.snk**、クリックして**開く**です。  
  
12. ソリューション エクスプ ローラーで右クリック**BTAHL7V231Common プロジェクト**、クリックして**展開**です。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。  
  
 進みます[手順 3: トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)です。