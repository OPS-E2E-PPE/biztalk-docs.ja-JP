---
title: '手順 2: の定義と Contoso のボキャブラリを公開 |Microsoft ドキュメント'
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
ms.openlocfilehash: 15937a1235cc1776be38fe2b0e5529c19d3f6fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211090"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a>手順 2: の定義と Contoso のボキャブラリを公開
このシナリオでは、緊急時でもインベントリが確実に利用できる状態にするビジネス ポリシーを Contoso で実装します。 ビジネス ポリシーは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] のビジネス ルール作成ツールを使用して作成します。 ここでは、ビジネス ポリシーを定義する際に使用するボキャブラリを作成します。  
  
### <a name="to-add-a-new-vocabulary"></a>新しいボキャブラリを追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。  
  
2.  [ルール ストアを開く] ダイアログ ボックスで、 **OK**です。  
  
3.  ファクト エクスプ ローラー ウィンドウで、上、**ボキャブラリ** タブを右クリックして**ボキャブラリ**、順にクリック**新しいボキャブラリの追加**です。  
  
4.  ボキャブラリの名前**3 a2priceavailabilityvocabulary**、キーを押します**Enter**です。  
  
### <a name="to-define-a-constant-vocabulary-value"></a>ボキャブラリの定数値を定義するには  
  
1.  ビジネス ルール作成ツール をクリックして**3 a2priceavailabilityvocabulary**を右クリックして**バージョン 1.0 (未保存)**、クリックして**新しい定義の追加**です。  
  
2.  **ボキャブラリの定義ウィザード**] ページで、[**定数値、値の範囲、または値セット**、クリックして **[次へ]** です。  
  
3.  **定数値、値の範囲、または値セット**] ページの [、**定義名**ボックスに、入力**Emergency Quantity Needed**、クリックして **[次へ]**.  
  
4.  **定数値の定義**] ページの [、**値**ボックスに、入力**800**、順にクリック**完了**です。  
  
### <a name="to-define-an-xml-document-get-element"></a>XML ドキュメントの "取得" 要素を定義するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilityvocabulary**、クリックして**新しい定義の追加**.  
  
2.  **VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリック**次**です。  
  
3.  **XML ドキュメントの要素または属性**] ページの [、**定義名**ボックスに、入力**Quantity Available**です。  
  
4.  をクリックして**参照**(横に、**スキーマ**フィールド) に移動、 **[contosopriceandavailability]** プロジェクト、ソリューション フォルダーは、select、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**開く**です。  
  
5.  バインドの選択 ダイアログ ボックスで、展開**rootPriceResponse**、展開**製品**を選択、 **numberavailable**要素、およびクリック**ok**.  
  
6.  **XML ドキュメントの要素または属性**] ページの [、**ドキュメントの種類**ボックスで、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  **操作を選択して**セクションで、選択 **「取得」操作の実行**、順にクリック**完了**です。  
  
### <a name="to-define-an-xml-document-set-element"></a>XML ドキュメントの "設定" 要素を定義するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilityvocabulary**、クリックして**新しい定義の追加**.  
  
2.  **VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリック**次**です。  
  
3.  **XML ドキュメントの要素または属性**] ページの [、**定義名**ボックスに、入力**Final Quantity Available**です。  
  
4.  をクリックして**参照**(横に、**スキーマ**フィールド) に移動、 **[contosopriceandavailability]** プロジェクト、ソリューション フォルダーは、select、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**開く**です。  
  
5.  **バインドの選択** ダイアログ ボックスで、展開**rootpriceresponse**、展開**製品**、クリックして、 **numberavailable**要素。 **[OK]** をクリックします。  
  
6.  **XML ドキュメントの要素または属性**] ページの [、**ドキュメントの種類**ボックスで、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  **操作を選択**セクションで、選択 **「セット」操作を実行する**、順にクリック**次**です。  
  
8.  **表示名を指定**] ページで [**完了**です。  
  
### <a name="to-save-and-publish-the-vocabulary"></a>ボキャブラリを保存および公開するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilityvocabulary**、クリックして**保存**です。  
  
2.  その同じを右クリックして**バージョン 1.0**ノードをクリックして**発行**です。  
  
    > [!NOTE]
    >  チュートリアルの次の手順で使用するため、ビジネス ルール作成ツールは開いたままにしておきます。  
  
## <a name="see-also"></a>参照  
 [手順 3: を定義する、発行、および Contoso のビジネス ポリシーを展開します。](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)