---
title: オーケストレーションでコントラクトの型指定されたエラーを処理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27a220e649b513ba70d3934bc0c74b71b865bea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337339"
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a>オーケストレーションで型指定されたエラー コントラクトを処理する方法
このトピックでは、オーケストレーション内から WCF サービスを使用するときに、型指定されたエラー コントラクトを処理する方法を説明します。 オーケストレーションで型指定されたエラー例外を処理するために消費している WCF サービスがあります、 **FaultContractAttribute**サービス操作に適用されるは、エラーをスローしてを使用してそのため、 **FaultException**\<T\> T が任意の有効なデータ コントラクトまたは WCF サービスから型をシリアル化可能なをすることができます。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a>オーケストレーションで型指定されたエラー コントラクトを処理するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、 をクリックし、**生成した項目の追加**します。  
  
2. **生成した項目の追加 - \<** <em>プロジェクト名</em>**\>**  ダイアログ ボックスで、**テンプレート** セクションで、選択**Consume WCF サービス**、 をクリックし、**追加**します。  
  
3. **BizTalk WCF サービス使用ウィザードへようこそ**] ページで [**次**します。  
  
4. **メタデータ ソース**] ページで、[ **Metadata Exchange (MEX) エンドポイント**、順にクリックします**次**します。  
  
5. **メタデータ エンドポイント**ページで、Ws-metadata Exchange または Http-get を通じてダウンロードのメタデータを提供する実行中のサービスの URL を指定 — たとえば、 http://localhost:8005 します。 URL からメタデータ ドキュメントを取得する次のようにクリックします。**取得**します。 実行中のサービスには、基本認証スキームでユーザーの資格情報が必要とする場合にクリックします**編集**を開く、 **BizTalk WCF サービス使用ウィザード** ダイアログ ボックスのユーザー名を入力し、実行中のサービスにアクセスするときに使用するパスワード。 **[次へ]** をクリックします。  
  
6. **WCF サービス メタデータの概要のインポート**ページで、設定を確認します。 クリックすることができます**戻る**変更を加えます。 クリックして**インポート**BizTalk アイテムと、WCF サービスを使用するために使用される型を作成します。  
  
7. **BizTalk WCF サービス使用ウィザードの完了**] ページで [**完了**します。  
  
8. 使用している WCF サービスが次のエラー例外をスローするとします。  
  
   ```  
   throw new FaultException<MyOperationException>(divideException);  
   ```  
  
    送信ポートでのエラー操作の種類のメッセージが必要ですが**MyOperationException**が WCF 応答メッセージには、エラー本文全体が含まれています。 そのため、抽出する必要があります、 **MyOperationException**一部構成することによって、メッセージから、**受信 BizTalk メッセージ本文**トランスポートのプロパティ ダイアログ ボックスのオプション。 例を次に示します。  
  
   -   選択**パス--本文のパスで見つかったコンテンツ**します。  
  
   -   次のボディ パス式を設定します。  
  
       ```  
       /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
       ```  
  
   -   選択**Xml**から、**ノード エンコード**ドロップダウン リスト。  
  
9. オーケストレーションでは、スコープと 2 つの例外ハンドラーを追加する必要があります。 1 つの例外ハンドラはエラー操作に似ています**MyOperationException** 、前の例に示すように、その他の例外ハンドラは汎用のキャッチ**SOAPExceptions**します。  
  
## <a name="see-also"></a>参照  
 [WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)   
 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)