---
title: "手順 5: Contoso プライベート プロセス オーケストレーションの変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, orchestrations
- private process tutorial, modifying private process orchestration
ms.assetid: a5430db8-e5f0-48a6-abb9-e268d8ec2ec4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a222ee518cf0555de60094411df73bf5a5d486a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-5-modifying-the-contoso-private-process-orchestration"></a>手順 5: Contoso プライベート プロセス オーケストレーションの変更
ここでは、プライベート プロセス オーケストレーションを変更して、Contoso のエンタープライズ リソース計画 (ERP) システムと統合します。 Contoso の ERP システムは、製品価格と在庫に対する内部的に定義されたスキーマを使用します。 3A2 - Price and Availability PIP (Partner Interface Process) のプライベート プロセスをカスタマイズすることによって、スキーマにマップされた情報を使用して、ERP システムと統合できるようになります。  
  
### <a name="to-add-a-reference-to-the-contoso-priceandavailability-and-rnpips-assemblies"></a>Contoso の PriceAndAvailability アセンブリおよび RNPIPs アセンブリの参照の追加  
  
1.  ソリューション エクスプ ローラーに表示される Contoso ソリューションを右クリックし、 **PrivateResponder**プロジェクトをクリックして**参照の追加**です。  
  
2.  [参照の追加] ダイアログ ボックスで、**参照**です。 移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin フォルダー、および、次のアセンブリを選択**:**  
  
    -   Microsoft.solutions.BTARN.CommonTypes.dll  
  
    -   Microsoft.solutions.BTARN.ConfigurationManager.dll  
  
    -   Microsoft.solutions.BTARN.GlobalSchemas.dll  
  
    -   Microsoft.solutions.BTARN.PublicResponder.dll  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll  
  
    -   Microsoft.solutions.BTARN.Shared.dll  
  
    -   Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll  
  
3.  **[追加]**をクリックします。  
  
4.  [参照の追加] ダイアログ ボックス、**プロジェクト**] タブで、[、 **[contosopriceandavailability]**と**HeaderHelper**プロジェクト、およびクリック**追加**です。  
  
5.  **[OK]**をクリックします。  
  
6.  [Microsoft 開発環境] ダイアログ ボックスで、 **OK**です。  
  
### <a name="to-create-new-message-types"></a>新しいメッセージの種類を作成するには  
  
1.  ソリューション エクスプ ローラーで、 **PrivateResponder**オーケストレーションを開きます。  
  
2.  ソリューション エクスプ ローラーでクリックして**オーケストレーション**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  [プロパティ] ウィンドウ内で、**識別子**ボックスに、入力**PIP3A2RequestMessage**です。  
  
5.  **メッセージの種類**ボックス、ドロップダウン矢印をクリックして、展開**スキーマ**、し、 **\<参照されたアセンブリから選択\>**です。  
  
6.  成果物 Typedialog の選択ボックスで、次のように選択します**Microsoft.Solutions.BTARN.Schemas.RNPIPs**左のペインで選択**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**右側のウィンドウで、。をクリックして**OK**です。  
  
7.  ソリューションに対して以下の情報を使用して手順 3. ～ 6. を繰り返し、すべてのメッセージの種類を作成します。  
  
    |[Identifier]|アセンブリ|メッセージの種類|  
    |----------------|--------------|------------------|  
    |PIP3A2ResponseMessage|Microsoft.Solutions.BTARN です。<br />Schemas.RNPips|_3A2PriceAndAvailability<br />ResponseMessageGuideline_v1_3|  
    |Contoso3A2ResponseMessage|ContosoPriceAndAvailability|rootPriceResponse|  
    |Contoso3A2RequestMessage|ContosoPriceAndAvailability|rootPriceRequest|  
  
8.  これで、このソリューションのメッセージの種類の作成が完了しました。  
  
### <a name="to-create-new-variables"></a>新しい変数を作成するには  
  
1.  オーケストレーション ビューで右クリック**変数、**  をクリックし、**新しい変数**です。  
  
2.  [プロパティ] ウィンドウ内で、**識別子**ボックスに、入力**contosoResponseXML**です。  
  
3.  **型**ボックスで、  **\<.NET クラス\>**ドロップダウン リストからです。  
  
4.  Select の成果物入力ダイアログ ボックスで、左側のウィンドウで、**現在のプロジェクト**と**参照**、ノードを選択**System.Xml**を選択**XmlDocument**をクリックして右側のペインの一覧から**OK**です。  
  
5.  **オーケストレーション ビュー**、 をクリックして**変数**、クリックして**新しい変数**です。  
  
6.  [プロパティ] ウィンドウ内で、**識別子**ボックスに、入力**submitMessage**です。  
  
7.  **型**ボックスで、  **\<.NET クラス\>**ドロップダウン リストからです。  
  
8.  成果物の種類の選択 ダイアログ ボックスの左側のウィンドウで展開**現在のプロジェクト**と**参照**、ノードを選択**Microsoft.Solutions.BTARN.Shared**の選択**SubmitRNIF**をクリックして右側のペインの一覧から**OK**です。  
  
### <a name="to-change-the-orchestration-filter-expression"></a>オーケストレーションのフィルター式を変更するには  
  
1.  オーケストレーション デザイナーで、選択、 **[receivefrompublicprocessresponder]**図形です。  
  
2.  プロパティ ウィンドウでの**フィルター式**ボックス、値 ボックスをクリックし、省略記号ボタンをクリックして (**.**) をフィルター式 ダイアログ ボックスを開きます。  
  
3.  フィルター式] ダイアログ ボックスで、 **Group By**セクションで、をクリックして、**または**値の最初の行にし、[ **AND**ドロップダウン リストからです。  
  
4.  フィルター式 ダイアログ ボックスで、**ここをクリックして新しい行を追加する**、し、 **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**ドロップダウン リストからです。  
  
5.  同じ行の **値**、しに入力**「3 a 2」**です。  
  
6.  同じ行の  **AND**で、 **Group By**ボックスし、**または**ドロップダウン リストからです。  
  
7.  [フィルター式] ダイアログ ボックスで、前の手順で作成した行を選択し、上矢印ボタンを 1 回クリックして行を上に移動します。  
  
8.  をクリックして**ここをクリックして新しい行を追加する**、し、 **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**ドロップダウン リストからです。  
  
9. 同じ行の **値**、しに入力**「3 a 2」**です。  
  
10. [OK] をクリックします。  
  
### <a name="to-modify-the-business-process-workflow"></a>ビジネス プロセスワークフローを変更するには  
  
1.  ドラッグ、**メッセージの割り当て**図形をツールボックスからデザイン画面に、下にドロップし、 **[receivefrompublicprocessresponder]**図形です。 選択、 **ConstructMessage_1**図形が作成されたし、[、**プロパティ**] ウィンドウで、**名前**ボックスに、入力**[constructpip3a2requestmessage]**.  
  
2.  ドラッグ、**変換**図形をデザイン画面に、下にドロップし、 **ConstructPIP3A2RequestMessage**図形です。 選択、 **ConstructMessage_1**図形が作成されたし、、**プロパティ**ウィンドウで、**名**ボックスに、入力**ConstructContoso3A2RequestMessage**.  
  
3.  ドラッグ、**送信**図形をデザイン画面に、下にドロップし、 **ConstructContoso3A2RequestMessage**図形です。  
  
4.  ドラッグ、**受信**図形をデザイン画面に、下にドロップし、 **Send_1**図形です。  
  
5.  オーケストレーション デザイン画面の空の領域をクリックします。  
  
6.  [プロパティ] ウィンドウで、選択、**トランザクションの種類**プロパティ、およびクリック**長時間**です。  
  
7.  ドラッグ、**スコープ**図形をデザイン画面に、下にドロップし、 **Receive_1**図形です。  
  
8.  [プロパティ] ウィンドウでから、**トランザクション タイプ**プロパティのドロップダウン リスト、選択**Atomic**の**スコープ**図形です。  
  
9. ドラッグ、**ルールの呼び出し**図形をデザイン画面にし、というラベルの上にドロップ**ツールボックスからここに図形をドロップ**内、**スコープ**図形です。 [プロパティ] ウィンドウで、**ルールの呼び出し**図形、**名前**ボックスに、入力**Execute3A2Vocabulary**です。  
  
10. ドラッグ、**変換**図形をデザイン画面に、下にドロップし、 **スコープ _ 1**図形です。 クリックして、 **ConstructMessage_1**図形です。 [プロパティ] ウィンドウでの**名前**ボックスに、入力**Construct3A2ResponseMessage**です。  
  
11. ドラッグ、**式**図形をデザイン画面に、下にドロップし、 **Construct3A2ResponseMessageTransform**図形です。  
  
12. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**をクリックして**すべてを保存**プロジェクトを保存します。  
  
## <a name="see-also"></a>参照  
 [手順 6: オーケストレーション図形の構成 (Contoso)](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)