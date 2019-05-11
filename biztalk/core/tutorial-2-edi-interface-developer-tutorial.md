---
title: チュートリアル 2:EDI インターフェイス開発チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1af388c62be4e23ba13d29f93567cdab76fdfb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401724"
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a>チュートリアル 2:EDI インターフェイス開発チュートリアル
このチュートリアルは、EDI 機能を使用する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターフェイス開発シナ リオでします。  
  
 **チュートリアルのシナリオ**  
  
 このシナリオで、取引先は ANSI X12 を使用して、会社に注文書を送信 Version 4010 850 トランザクション セット (850 メッセージ)。 会社が、注文システムの内部アプリケーションを使用して、発注書を処理します。  
  
 取引先から受信する 850 メッセージと、会社の内部の注文システム間のインターフェイスの設計を担当するインターフェイス開発者としています。 取引先には、送信 850 メッセージごとの機能確認 (997) が必要です。  
  
 参照しやすいように、次の識別子が使用されます。  
  
|Entity|[Identifier]|  
|------------|----------------|  
|会社|OrderSystem|  
|取引先パートナー|Fabrikam|  
  
 完成したソリューションにおけるメッセージ フローは次のようになります。  
  
 ![EDI インターフェイス開発チュートリアル メッセージ フロー](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")  
  
 **メッセージ フロー**  
  
 このチュートリアルでは、ソリューションは、次の操作を行います。  
  
1. Fabrikam 取引先からフラット ファイル インターチェンジを受信します。  
  
   > [!NOTE]
   >  この一覧のイベントは、示されている順序で発生するとは限りません。  
  
2. EDI インターチェンジをそのスキーマに対して検証し、メッセージを XML に逆アセンブルして、メッセージ XML を MessageBox にドロップします。  
  
3. 受信した EDI インターチェンジに対する 997 受信確認を生成して、MessageBox にドロップします。  
  
4. 一方向の送信ポートで 997 XML を取得し、997 EDI インターチェンジをアセンブルします。  
  
5. 997 インターチェンジを Fabrikam に送信します。  
  
6. 一方向の送信ポートで Msg XML を選択し、メッセージ EDI インターチェンジをアセンブルします。  
  
7. EDI インターチェンジを OrderSystem に送信します。  
  
   **Configuration**  
  
   このチュートリアルでは、次の作業を行います。  
  
- BizTalk 取引先から 850 メッセージを期待し、997 受信確認を返信するを構成します。  
  
- BizTalk マップを使用して、850 メッセージ データを注文システムで必要な形式に変換します。 このマップは、チュートリアル ファイルで提供される、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK。  
  
- 850 メッセージを受信するための受信ポートを構成します。  
  
- OrderSystem に正しい形式で 850 メッセージを送信する送信ポートを構成します。  
  
- BizTalk で生成された 997 受信確認を取引先 Fabrikam にルーティングをサブスクライブする送信ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: EDI インターフェイス開発チュートリアルを準備します。](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [手順 2:更新し、チュートリアルのソリューションの展開](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [ステップ 3:組織のパーティとビジネス プロファイルを構成します。](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [手順 4:取引先のパーティとビジネス プロファイルを構成します。](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [手順 5:構成を受信ポートと受信場所](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [手順 6:組織にデータを送信する送信ポートの構成します。](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [手順 7:取引先に、受信確認を送信する送信ポートの構成します。](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [手順 8:当事者間で取引先アグリーメントを構成します。](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [手順 9:EDI ソリューションをテストします。](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)