---
title: '手順 2: v2.3.1 の一般的なスキーマの追加 |Microsoft Docs'
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
ms.openlocfilehash: 36b07419b50d02d1f810dffbd7417533e844a3ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994163"
---
# <a name="step-2-add-common-schemas-for-v231"></a>手順 2: v2.3.1 の一般的なスキーマを追加します。
この手順では、BTAHL7231Common プロジェクト テンプレートに基づいて新しいプロジェクトを作成します。 このテンプレートが含まれています (データ型、セグメント、およびテーブルの値) の 3 つの一般的なスキーマには Microsoft BizTalk Accelerator には用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) v2.3.1 メッセージ インスタンスの検証に使用します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 受信バッチの個々 のメッセージに使用するスキーマを含む、HL7 v2.3.1 スキーマと共にこれらの一般的なスキーマを使用して (ADT ^ A03)。  
  
 ステップの最後に、アセンブリに厳密なキーを割り当てるし、デプロイします。 2 番目の強力なキーを作成する必要はありません。作成した厳密なキーを使用して[手順 1: ヘッダーの追加と確認スキーマ](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)します。  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a>V2.3.1 の一般的なスキーマを追加し、アセンブリを展開するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
2. 新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。  
  
3. **テンプレート**セクションで、 **BTAHL7V231Common プロジェクト**します。  
  
4. **名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。  
  
5. **ソリューション**ボックスで、**ソリューションに追加**します。  
  
6. **[OK]** をクリックします。  
  
   > [!NOTE]
   >  ソリューション エクスプ ローラーでプロジェクトの 3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) が含まれます。  
  
7. ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Common プロジェクト**、 をクリックし、**プロパティ**します。  
  
8. BTAHL7V231Common プロパティ ページ ダイアログ ボックスで、をクリックして**署名**します。  
  
9. 確認**アセンブリに署名**チェック ボックスをオンします。  
  
10. 厳密な名前キー ファイルの選択 でドロップダウン リストを選択します。  
  
11. 参照 **: \Batching チュートリアル**を選択します**key.snk**、 をクリックし、**オープン**します。  
  
12. 右クリック**BTAHL7V231Common**、 をクリックし、**デプロイ**します。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。  
  
    続行する[手順 3: トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)します。