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
ms.openlocfilehash: bcd7f7d08e1451bfe50d2558b8f7c6b24d897957
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283608"
---
# <a name="hubscenario-sample"></a>HubScenario サンプル
HubScenario サンプルでは、ハブ シナリオでのメッセージ送信を管理する方法を示します。 最終的な受信者に送信されるメッセージに中間ハブに送信されるメッセージを変換します。  
  
 HubScenario は、サービスのコンテンツから最終受信者の DUNS 番号を抽出します。 署名と暗号化の証明書、および送信先の URL を管理します。 最終的な受信者に新しいメッセージを生成します。  
  
 このサンプルでは、3A4 要求と応答メッセージ、および 0 の C 1 つの要求メッセージを処理します。 HubScenario を使用して、目的のアプリケーションを作成するときに各メッセージ プロセス PIP (Partner Interface) のルーチンを生成する必要があります。  
  
 HubScenario サンプルには、プロジェクトと HubScenario.odx プロジェクトが含まれています。  
  
 HubScenario サンプルには、HubScenario.odx オーケストレーションで使用するための受信ポート (MessagesToLOB_Receive_Port) のバインドをインポートして、受信場所 (MessagesToLOB_Receive_Location) を使用できるバインド ファイルも含まれています。 このバインド ファイル (HubScenarioBinding.xml) にある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet \SDK\HubScenario します。 バインドをインポートするのにには、BTSTask コマンドを使用します。 詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」のトピックを参照してください。  
  
### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1. Visual Studio で開く\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>RosettaNet\SDK\HubScenario\HubScenario.btproj のアクセラレータです。 ソリューション エクスプ ローラーで HubScenario プロジェクトを右クリックし、し、[プロパティ] をクリックします。 HubScenario プロジェクトのプロパティ ページで、署名 タブで選択**アセンブリに署名** チェック ボックスを選択し、 **HubScenario.snk**で**厳密な名前キーファイルを選択して**クリック**Ok**します。  
  
2. ソリューション エクスプ ローラーで HubHelper プロジェクトを右クリックし、し、[プロパティ] をクリックします。 HubHelper プロジェクトのプロパティ ページで、署名 タブでサインオン アセンブリのチェック ボックスを確認します。 厳密な名前キー ファイルのフィールドを選択して、新しい種類の選択**HubHelper.snk**キー ファイル名をクリックします**OK**します。  
  
   > [!NOTE]
   >  HubScenario および HubHelper プロジェクトでアセンブリ キー ファイルを手動で入力はない場合、アセンブリは展開しません。  
  
3. コマンド プロンプトに移動します。 *\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\hubscenario フォルダー。 ファイル Setup.bat を実行します (または、64 ビット コンピューターで Setupx64.bat を実行します。)  
  
## <a name="demonstrates"></a>使用例  
 HubScenario.ods オーケストレーションでは、次のタスクを実行する方法を示します。  
  
1. 基幹業務アプリケーションからメッセージを受信します。  
  
2. 削除、`CDATA`から、サービス コンテンツを XML 文字列を返す要素。  
  
3. 最後のメッセージの送信先パーティ名、PIPCode、PIPInstanceID、および PIPVersion を取得します。  
  
4. 最終の受信者の DUNS 番号を取得します。  
  
5. メッセージのカテゴリを指定し、サービスのコンテンツを適切なスキーマへの参照を含む DOCTYPE 要素を追加します。  
  
6. 新しい送信先パーティ名、DUNS 番号、PIP コード情報、およびサービスのコンテンツを含むメッセージを構築します。  
  
7. 処理するためのメッセージを送信する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。 これは、呼び出しを`SubmitRNIF.SubmitMessage`します。  
  
## <a name="see-also"></a>参照  
 [サンプルのハブベース シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)