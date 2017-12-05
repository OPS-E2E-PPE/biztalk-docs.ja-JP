---
title: "HubScenario サンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47f7ba8320a43cbfdc98a3b3e5becdce9a898f9
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="hubscenario-sample"></a>HubScenario サンプル
HubScenario サンプルは、ハブ シナリオでのメッセージの送信を管理する方法を示します。 このサンプルでは、中間のハブに送信されたメッセージを最終受信者に送信するメッセージに変換します。  
  
 HubScenario は、サービス コンテンツから最終受信者の DUNS 番号を抽出します。 さらに、著名証明書、暗号化証明書、および送信先 URL を管理します。 そして、最終受信者への新しいメッセージを生成します。  
  
 このサンプルでは、3A4 要求メッセージと応答メッセージ、および 0C1 要求メッセージを取り扱います。 HubScenario を使用して各自の目的に合ったアプリケーションを作成するには、各メッセージ PIP (Partner Interface Process) に対してルーチンを生成する必要があります。  
  
 HubScenario サンプルには、HubHelper.cs プロジェクトと HubScenario.odx プロジェクトが含まれます。  
  
 HubScenario サンプルには、受信ポート (MessagesToLOB_Receive_Port) と受信場所 (MessagesToLOB_Receive_Location) のバインドのインポートに使用できるバインド ファイルも含まれます。 このバインド ファイル (HubScenarioBinding.xml) にあります*\<ドライブ\>*: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk\<バージョン\>アクセラレータRosettaNet \SDK\HubScenario です。 バインドのインポートには BTSTask コマンドを使用します。 詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」を参照してください。  
  
### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  Visual Studio で開く\<ドライブ\>: \Program Files\Microsoft Microsoft BizTalk\<バージョン\>RosettaNet\SDK\HubScenario\HubScenario.btproj のアクセラレータです。 ソリューション エクスプローラーで HubScenario プロジェクトを右クリックし、[プロパティ] をクリックします。 HubScenario プロジェクトの プロパティ ページで 署名 タブを選択**アセンブリに署名** チェック ボックスを選択して**HubScenario.snk**で**厳密な名前キーファイルを選択して** をクリック**Ok**です。  
  
2.  ソリューション エクスプローラーで HubHelper プロジェクトを右クリックして、[プロパティ] をクリックします。 HubHelper プロジェクトのプロパティ ページの [署名] タブで、[アセンブリの署名] チェック ボックスをオンにします。 厳密な名前キー ファイルのフィールドを選択して、新しい種類を選択**HubHelper.snk**キー ファイル名とクリック**OK**です。  
  
    > [!NOTE]
    >  HubScenario および HubHelper プロジェクトに手動でアセンブリ キー ファイルを入力しないと、これらのアセンブリは展開されません。  
  
3.  コマンド プロンプトに移動*\<ドライブ\>*: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\HubScenario フォルダーです。 ファイル Setup.bat を実行します (64 ビット コンピューターの場合は、Setupx64.bat を実行します)。  
  
## <a name="demonstrates"></a>使用例  
 HubScenario.ods オーケストレーションは、次のタスクを実行する方法を示します。  
  
1.  基幹業務アプリケーションからメッセージを受信する。  
  
2.  Service Content から `CDATA` 要素を削除し、XML 文字列を返す。  
  
3.  最終メッセージの相手側パーティ名、PIPCode、PIPInstanceID、PIPVersion を取得する。  
  
4.  最終受信者の DUNS 番号を取得する。  
  
5.  メッセージのカテゴリを判断し、正しいスキーマへの参照を含んでいる DOCTYPE 要素をサービス コンテンツに追加する。  
  
6.  新しい相手側パーティ名、DUNS 番号、PIP コード情報、およびサービス コンテンツによりメッセージを構築する。  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] で処理するために、メッセージを送信する。 これにより、`SubmitRNIF.SubmitMessage` を呼び出します。  
  
## <a name="see-also"></a>参照  
 [サンプルのハブベース シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)