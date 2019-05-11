---
title: 手順 2:V2.3.1 の一般的なスキーマを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, common schemas
- common schemas
ms.assetid: db1a2206-559f-475a-803d-55522cce007e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 869eadf2c52b9def861aa93d451ca8c53bfcb26e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289009"
---
# <a name="step-2-create-common-schemas-for-v231"></a>手順 2:V2.3.1 の一般的なスキーマを作成します。
V2.3.1 スキーマは、頻繁に参照されるスキーマは、メッセージ インスタンスの検証に使用します。  
  
### <a name="to-create-a-common-schema-for-v231"></a>V2.3.1 の一般的なスキーマを作成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
2. 新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。  
  
3. [テンプレート] セクションで**BTAHL7V231Common プロジェクト**します。  
  
4. **名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。  
  
5. **ソリューション**ボックスで、**ソリューションに追加**します。  
  
6. **[OK]** をクリックします。  
  
   > [!NOTE]
   >  ソリューション エクスプ ローラーでプロジェクトの 3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) が含まれます。  
  
7. ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Common プロジェクト**、 をクリックし、**プロパティ**します。  
  
8. BTAHL7V231Common プロパティ ページで、次のようにクリックします。**署名**します。  
  
9. 選択、**アセンブリに署名**チェック ボックスをオンします。  
  
10. **厳密な名前キー ファイルを選択して**を選択します**\<を参照しています.\>** .  
  
11. 参照\<ドライブ\>: \Batching チュートリアルでは、選択**key.snk**、 をクリックし、**オープン**します。  
  
12. ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Common プロジェクト**、 をクリックし、**デプロイ**します。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。  
  
    続行する[手順 3。トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)します。