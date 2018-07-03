---
title: '手順 2: 定義と Contoso のボキャブラリを公開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, creating
- vocabularies, publishing
- private process tutorial, creating vocabularies
ms.assetid: e23880c0-772c-48c6-a6b5-32eb951527c8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56dc5a4c65dcf198308e382b82d9b167c5d4ca8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007107"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a>手順 2: 定義と Contoso のボキャブラリを公開
このシナリオでは、緊急時でもインベントリが確実に利用できる状態にするビジネス ポリシーを Contoso で実装します。 ビジネス ポリシーは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] のビジネス ルール作成ツールを使用して作成します。 ここでは、ビジネス ポリシーを定義する際に使用するボキャブラリを作成します。  
  
### <a name="to-add-a-new-vocabulary"></a>新しいボキャブラリを追加するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。  
  
2. [ルール ストアを開く] ダイアログ ボックスで、 **OK**します。  
  
3. ファクト エクスプローラ ペインでの**ボキャブラリ** タブで、右クリック**ボキャブラリ**、 をクリックし、**新しいボキャブラリの追加**。  
  
4. ボキャブラリの名前**3 a2priceavailabilityvocabulary**、およびキーを押します**Enter**します。  
  
### <a name="to-define-a-constant-vocabulary-value"></a>ボキャブラリの定数値を定義するには  
  
1.  ビジネス ルール作成ツール をクリックして**3 a2priceavailabilityvocabulary**、右クリック**バージョン 1.0 (未保存)**、 をクリックし、**新しい定義の追加**します。  
  
2.  **ボキャブラリの定義ウィザード**] ページで、[**定数値、値の範囲、または値セットの**、順にクリックします**次**します。  
  
3.  **定数値、値の範囲、または値セットの** ページの 、**定義名**ボックスに「 **Emergency Quantity Needed**、 をクリックし、 **次へ**.  
  
4.  **定数値の定義**] ページの [、**値**ボックスに「 **800**、順にクリックします**完了**します。  
  
### <a name="to-define-an-xml-document-get-element"></a>XML ドキュメントの "取得" 要素を定義するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)** [ **3 a2priceavailabilityvocabulary**、] をクリックし、**新しい定義の追加**.  
  
2.  **VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリックします**次**します。  
  
3.  **XML ドキュメントの要素または属性**ページで、**定義名**ボックスに「 **Quantity Available**します。  
  
4.  をクリックして**参照**(横に、**スキーマ**フィールド)、移動、 **[contosopriceandavailability]** 選択、ソリューション フォルダー内のプロジェクト、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**オープン**します。  
  
5.  バインドの選択 ダイアログ ボックスで、 **rootPriceResponse**、展開**製品**を選択、 **NumberAvailable**要素、およびクリック**ok**.  
  
6.  **XML ドキュメントの要素または属性**ページで、**ドキュメントの種類**ボックスに、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  **操作を選択して**セクションで、選択 **「取得」操作の実行**、順にクリックします**完了**します。  
  
### <a name="to-define-an-xml-document-set-element"></a>XML ドキュメントの "設定" 要素を定義するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)** [ **3 a2priceavailabilityvocabulary**、] をクリックし、**新しい定義の追加**.  
  
2.  **VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリックします**次**します。  
  
3.  **XML ドキュメントの要素または属性**ページで、**定義名**ボックスに「 **Final Quantity Available**します。  
  
4.  をクリックして**参照**(横に、**スキーマ**フィールド)、移動、 **[contosopriceandavailability]** 選択、ソリューション フォルダー内のプロジェクト、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**オープン**します。  
  
5.  **バインドの選択** ダイアログ ボックスで、展開**rootPriceResponse**、展開**製品**を選び、 **NumberAvailable**要素。 **[OK]** をクリックします。  
  
6.  **XML ドキュメントの要素または属性**ページで、**ドキュメントの種類**ボックスに、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  **操作を選択して**セクションで、選択 **「設定」操作を実行する**、順にクリックします **[次へ]** します。  
  
8.  **表示名を指定**] ページで [**完了**します。  
  
### <a name="to-save-and-publish-the-vocabulary"></a>ボキャブラリを保存および公開するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)** [ **3 a2priceavailabilityvocabulary**、] をクリックし、**保存**します。  
  
2.  右クリックしてその同じ**バージョン 1.0**ノードをクリック**発行**します。  
  
    > [!NOTE]
    >  チュートリアルの次の手順で使用するため、ビジネス ルール作成ツールは開いたままにしておきます。  
  
## <a name="see-also"></a>参照  
 [手順 3: Contoso のビジネス ポリシーの定義、公開、展開](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)