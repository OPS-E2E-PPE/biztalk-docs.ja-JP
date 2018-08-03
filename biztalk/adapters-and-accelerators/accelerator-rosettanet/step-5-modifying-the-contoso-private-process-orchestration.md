---
title: '手順 5: Contoso プライベート プロセス オーケストレーションの変更 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, orchestrations
- private process tutorial, modifying private process orchestration
ms.assetid: a5430db8-e5f0-48a6-abb9-e268d8ec2ec4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 197854a1a37846a11b07b126ec73cb7f204d91b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972899"
---
# <a name="step-5-modifying-the-contoso-private-process-orchestration"></a>手順 5: Contoso プライベート プロセス オーケストレーションの変更
ここでは、プライベート プロセス オーケストレーションを変更して、Contoso のエンタープライズ リソース計画 (ERP) システムと統合します。 Contoso の ERP システムは、製品価格と在庫に対する内部的に定義されたスキーマを使用します。 3A2 - Price and Availability PIP (Partner Interface Process) のプライベート プロセスをカスタマイズすることによって、スキーマにマップされた情報を使用して、ERP システムと統合できるようになります。  
  
### <a name="to-add-a-reference-to-the-contoso-priceandavailability-and-rnpips-assemblies"></a>Contoso の PriceAndAvailability アセンブリおよび RNPIPs アセンブリの参照の追加  
  
1. ソリューション エクスプ ローラーに表示される Contoso ソリューションを右クリックし、 **PrivateResponder**プロジェクトをクリックして**参照の追加**します。  
  
2. [参照の追加] ダイアログ ボックスで、**参照**します。 移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin フォルダーを選択し、次のアセンブリ<strong>:</strong>  
  
   -   Microsoft.solutions.BTARN.CommonTypes.dll  
  
   -   Microsoft.solutions.BTARN.ConfigurationManager.dll  
  
   -   Microsoft.solutions.BTARN.GlobalSchemas.dll  
  
   -   Microsoft.solutions.BTARN.PublicResponder.dll  
  
   -   Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll  
  
   -   Microsoft.solutions.BTARN.Shared.dll  
  
   -   Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll  
  
3. **[追加]** をクリックします。  
  
4. 参照の追加] ダイアログ ボックスで、[、**プロジェクト**] タブで、[、 **ContosoPriceAndAvailability**と**HeaderHelper**プロジェクト、およびクリック**追加**します。  
  
5. **[OK]** をクリックします。  
  
6. マイクロソフトの開発環境] ダイアログ ボックスで、[ **OK**します。  
  
### <a name="to-create-new-message-types"></a>新しいメッセージの種類を作成するには  
  
1.  ソリューション エクスプ ローラーで、 **PrivateResponder**オーケストレーションを開きます。  
  
2.  ソリューション エクスプ ローラーでクリックして**オーケストレーション**します。  
  
3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
4.  プロパティ ウィンドウでの**識別子**ボックスに「 **PIP3A2RequestMessage**します。  
  
5.  **メッセージの種類**ボックス、ドロップダウン矢印をクリックして、展開**スキーマ**、し、 **\<参照されたアセンブリから選択\>** します。  
  
6.  成果物のタイプの選択ボックスで、次のように選択します **[microsoft.solutions.btarn.schemas.rnpips]** 左側のウィンドウで次のように選択します。 **_ 3 a2priceandavailabilityquerymessageguideline_v1_3**右側のウィンドウで、。クリックして**OK**します。  
  
7.  ソリューションに対して以下の情報を使用して手順 3. ～ 6. を繰り返し、すべてのメッセージの種類を作成します。  
  
    |[Identifier]|アセンブリ|メッセージ型|  
    |----------------|--------------|------------------|  
    |PIP3A2ResponseMessage|Microsoft.Solutions.BTARN します。<br />Schemas.RNPips|_3A2PriceAndAvailability<br />ResponseMessageGuideline_v1_3|  
    |Contoso3A2ResponseMessage|ContosoPriceAndAvailability|rootPriceResponse|  
    |Contoso3A2RequestMessage|ContosoPriceAndAvailability|rootPriceRequest|  
  
8.  これで、このソリューションのメッセージの種類の作成が完了しました。  
  
### <a name="to-create-new-variables"></a>新しい変数を作成するには  
  
1.  オーケストレーション ビューで右クリックして**変数、**  をクリックし、**新しい変数**します。  
  
2.  [プロパティ] ウィンドウでの**識別子**ボックスに「 **contosoResponseXML**します。  
  
3.  **型**ボックスで、  **\<.NET クラス\>** ドロップダウン リストから。  
  
4.  入力 ダイアログ ボックスで、左側のウィンドウで 成果物で、**現在プロジェクト**と**参照**、ノードを選択**System.Xml**を選択します**XmlDocument** 、右側のウィンドウとクリックの一覧から**OK**します。  
  
5.  **オーケストレーション**、 をクリックして**変数**、 をクリックし、**新しい変数**。  
  
6.  [プロパティ] ウィンドウでの**識別子**ボックスに「 **submitMessage**します。  
  
7.  **型**ボックスで、  **\<.NET クラス\>** ドロップダウン リストから。  
  
8.  成果物の種類の選択 ダイアログ ボックスの左側のウィンドウで**現在プロジェクト**と**参照**、ノードを選択**Microsoft.Solutions.BTARN.Shared**を選択します。**SubmitRNIF** 、右側のウィンドウとクリックの一覧から**OK**します。  
  
### <a name="to-change-the-orchestration-filter-expression"></a>オーケストレーションのフィルター式を変更するには  
  
1.  オーケストレーション デザイナーで、選択、 **[receivefrompublicprocessresponder]** 図形。  
  
2.  プロパティ ウィンドウ内で、**フィルター式**ボックスで、値 ボックスをクリックし、省略記号ボタンをクリックして (**...**) フィルター式 ダイアログ ボックスを開きます。  
  
3.  フィルター式] ダイアログ ボックスでの**Group By**セクションで、[、**または**最初の行に値を選び**AND**ドロップダウン リストから。  
  
4.  フィルター式 ダイアログ ボックスで、**ここをクリックして新しい行を追加する**、し、 **microsoft.solutions.btarn.globalschemas.scpipcode**ドロップダウン リストから。  
  
5.  同じ行内では、次のようにクリックします。**値**、にを入力し、 **"3 a 2"** します。  
  
6.  同じ行内では、次のようにクリックします。 **AND**で、 **Group By**ボックスを選び**または**ドロップダウン リストから。  
  
7.  [フィルター式] ダイアログ ボックスで、前の手順で作成した行を選択し、上矢印ボタンを 1 回クリックして行を上に移動します。  
  
8.  クリックして**ここをクリックして新しい行を追加する**、し、 **microsoft.solutions.btarn.globalschemas.scpipcode**ドロップダウン リストから。  
  
9. 同じ行内では、次のようにクリックします。**値**、にを入力し、 **"3 a 2"** します。  
  
10. [OK] をクリックします。  
  
### <a name="to-modify-the-business-process-workflow"></a>ビジネス プロセスワークフローを変更するには  
  
1. ドラッグ、**メッセージの割り当て**図形をツールボックスからデザイン画面に、下にドロップし、 **[receivefrompublicprocessresponder]** 図形。 選択、 **[constructmessage_1]** が作成された図形と、**プロパティ**ウィンドウで、**名前**ボックスに「 **[constructpip3a2requestmessage]**.  
  
2. ドラッグ、**変換**図形をデザイン画面に、下にドロップし、 **ConstructPIP3A2RequestMessage**図形。 選択、 **[constructmessage_1]** が作成された図形と、**プロパティ**ウィンドウで、**名前**ボックスに「 **[constructcontoso3a2requestmessage]**.  
  
3. ドラッグ、**送信**図形をデザイン画面に、下にドロップし、 **ConstructContoso3A2RequestMessage**図形。  
  
4. ドラッグ、**受信**図形をデザイン画面に、下にドロップし、 **Send_1**図形。  
  
5. オーケストレーション デザイン画面の空の領域をクリックします。  
  
6. プロパティ ウィンドウで、選択、**トランザクションの種類**プロパティ、およびクリック**長時間**します。  
  
7. ドラッグ、**スコープ**図形をデザイン画面に、下にドロップし、 **Receive_1**図形。  
  
8. [プロパティ] ウィンドウでから、**トランザクションの種類**プロパティのドロップダウン リスト、選択**アトミック**の**スコープ**図形。  
  
9. ドラッグ、**ルールの呼び出し**図形をデザイン画面にしと書かれたラベルにドロップ**ここで、ツールボックスから図形をドロップ**内で、**スコープ**図形。 [プロパティ] ウィンドウで、**ルールの呼び出し**図形、**名前**ボックスに「 **Execute3A2Vocabulary**します。  
  
10. ドラッグ、**変換**図形をデザイン画面に、下にドロップし、 **Scope_1**図形。 をクリックして、 **ConstructMessage_1**図形。 [プロパティ] ウィンドウでの**名前**ボックスに「 **Construct3A2ResponseMessage**します。  
  
11. ドラッグ、**式**図形をデザイン画面に、下にドロップし、 **Construct3A2ResponseMessageTransform**図形。  
  
12. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**、 をクリックして**すべて保存**プロジェクトを保存します。  
  
## <a name="see-also"></a>参照  
 [手順 6: オーケストレーション図形の構成 (Contoso)](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)