---
title: "チュートリアル 2: EDI インターフェイス開発チュートリアル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb84454d2570ae6833847b598b55af6cf7777e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a>チュートリアル 2: EDI インターフェイス開発チュートリアル
このチュートリアルでは、インターフェイス開発シナリオで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI 機能を使用する方法について説明します。  
  
 **チュートリアルのシナリオ**  
  
 このシナリオでは、取引先は ANSI X12 Version 4010 850 トランザクション セット (850 メッセージ) を使用して注文書を送信します。 社内では、内部アプリケーション、注文システムを使用して、発注書を処理します。  
  
 インターフェイス開発者として、取引先から受信した 850 のメッセージと社内の注文システムとの間のインターフェイスを設計するとします。 取引先は、送信する 850 メッセージごとに機能確認 (997) を要求します。  
  
 参照しやすいように、次の識別子を使用します。  
  
|Entity|[Identifier]|  
|------------|----------------|  
|自社|OrderSystem|  
|取引先|Fabrikam|  
  
 完成したソリューションにおけるメッセージ フローは次のとおりです。  
  
 ![EDI インターフェイス開発チュートリアル メッセージ フロー](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")  
  
 **メッセージ フロー**  
  
 このチュートリアルのソリューションは次のとおりです。  
  
1.  Fabrikam という取引先からフラット ファイル インターチェンジを受信します。  
  
    > [!NOTE]
    >  この一覧のイベントは、示されている順序で発生するとは限りません。  
  
2.  EDI インターチェンジをそのスキーマに対して検証し、メッセージを XML に逆アセンブルして、メッセージ XML を MessageBox にドロップします。  
  
3.  受信した EDI インターチェンジに対する 997 受信確認を生成して、MessageBox にドロップします。  
  
4.  一方向の送信ポートで 997 XML を取得し、997 EDI インターチェンジをアセンブルします。  
  
5.  997 インターチェンジを Fabrikam に送信します。  
  
6.  一方向の送信ポートで Msg XML を取得し、メッセージ EDI インターチェンジをアセンブルします。  
  
7.  EDI インターチェンジを OrderSystem に送信します。  
  
 **Configuration**  
  
 このチュートリアルでは、次の作業を行います。  
  
-   取引先から送信される 850 メッセージを予想して BizTalk を構築し、997 受信確認を送り返します。  
  
-   BizTalk マップを使用して、850 メッセージのデータを注文システムで必要な形式に変換します。 このマップは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK のチュートリアル ファイルに収録されています。  
  
-   850 メッセージの受信に使用する受信ポートを構成します。  
  
-   OrderSystem に正しい形式で 850 メッセージを送信するように送信ポートを構成します。  
  
-   BizTalk で生成された 997 受信確認をルーティングして取引先の Fabrikam に返すため、これをサブスクライブするように送信ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: EDI インターフェイス開発チュートリアルの準備します。](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [手順 2: 更新し、チュートリアルのソリューションを展開](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [手順 3: 組織のパーティとビジネス プロファイルを構成します。](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [手順 4: 取引先のパーティとビジネス プロファイルを構成します。](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [手順 5: 構成する受信ポートと受信場所](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [手順 6: 組織にデータを送信する送信ポートを構成します。](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [手順 7: 取引先に、受信確認を送信する送信ポートを構成します。](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [手順 8: 当事者間の取引先アグリーメントを構成します。](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [手順 9: EDI ソリューションをテストします。](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)