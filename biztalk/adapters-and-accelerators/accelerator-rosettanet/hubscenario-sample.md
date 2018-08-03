---
title: HubScenario サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1b3274108d6a8cac25e58958a6bdea530027f36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970203"
---
# <a name="hubscenario-sample"></a>HubScenario サンプル
HubScenario サンプルは、ハブ シナリオでのメッセージの送信を管理する方法を示します。 このサンプルでは、中間のハブに送信されたメッセージを最終受信者に送信するメッセージに変換します。  
  
 HubScenario は、サービス コンテンツから最終受信者の DUNS 番号を抽出します。 さらに、著名証明書、暗号化証明書、および送信先 URL を管理します。 そして、最終受信者への新しいメッセージを生成します。  
  
 このサンプルでは、3A4 要求メッセージと応答メッセージ、および 0C1 要求メッセージを取り扱います。 HubScenario を使用して各自の目的に合ったアプリケーションを作成するには、各メッセージ PIP (Partner Interface Process) に対してルーチンを生成する必要があります。  
  
 HubScenario サンプルには、HubHelper.cs プロジェクトと HubScenario.odx プロジェクトが含まれます。  
  
 HubScenario サンプルには、受信ポート (MessagesToLOB_Receive_Port) と受信場所 (MessagesToLOB_Receive_Location) のバインドのインポートに使用できるバインド ファイルも含まれます。 このバインド ファイル (HubScenarioBinding.xml) にある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet \SDK\HubScenario します。 バインドのインポートには BTSTask コマンドを使用します。 詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」のトピックを参照してください。  
  
### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1. Visual Studio で開く\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>RosettaNet\SDK\HubScenario\HubScenario.btproj のアクセラレータです。 ソリューション エクスプローラーで HubScenario プロジェクトを右クリックし、[プロパティ] をクリックします。 HubScenario プロジェクトのプロパティ ページで、署名 タブで選択**アセンブリに署名** チェック ボックスを選択し、 **HubScenario.snk**で**厳密な名前キーファイルを選択して**クリック**Ok**します。  
  
2. ソリューション エクスプローラーで HubHelper プロジェクトを右クリックして、[プロパティ] をクリックします。 HubHelper プロジェクトのプロパティ ページの [署名] タブで、[アセンブリの署名] チェック ボックスをオンにします。 厳密な名前キー ファイルのフィールドを選択して、新しい種類の選択**HubHelper.snk**キー ファイル名をクリックします**OK**します。  
  
   > [!NOTE]
   >  HubScenario および HubHelper プロジェクトに手動でアセンブリ キー ファイルを入力しないと、これらのアセンブリは展開されません。  
  
3. コマンド プロンプトに移動します。 *\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\hubscenario フォルダー。 ファイル Setup.bat を実行します (64 ビット コンピューターの場合は、Setupx64.bat を実行します)。  
  
## <a name="demonstrates"></a>使用例  
 HubScenario.ods オーケストレーションは、次のタスクを実行する方法を示します。  
  
1. 基幹業務アプリケーションからメッセージを受信する。  
  
2. Service Content から `CDATA` 要素を削除し、XML 文字列を返す。  
  
3. 最終メッセージの相手側パーティ名、PIPCode、PIPInstanceID、PIPVersion を取得する。  
  
4. 最終受信者の DUNS 番号を取得する。  
  
5. メッセージのカテゴリを判断し、正しいスキーマへの参照を含んでいる DOCTYPE 要素をサービス コンテンツに追加する。  
  
6. 新しい相手側パーティ名、DUNS 番号、PIP コード情報、およびサービス コンテンツによりメッセージを構築する。  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] で処理するために、メッセージを送信する。 これにより、`SubmitRNIF.SubmitMessage` を呼び出します。  
  
## <a name="see-also"></a>参照  
 [サンプルのハブベース シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)