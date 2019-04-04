---
title: AS2 BizTalk Server での処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0027d3db-24a5-459d-9f4e-a75f49d31d82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69c778df5ccafc11a5a3a8aef4326138d54c4596
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013083"
---
# <a name="as2-processing-in-biztalk-server"></a>BizTalk Server での AS2 処理
このトピックでは、AS2 メッセージの受信側と送信側の処理、および取引先アグリーメントが AS2 メッセージングにどのように役立つかの概要について説明します。  
  
## <a name="trading-partner-agreements-for-as2-processing"></a>AS2 処理用の取引先アグリーメント  
 取引先アグリーメントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における AS2 のサポートで重要な役割を果たします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における AS2 処理に関連したほとんどの構成機能および管理機能は、ビジネス プロファイル間の取引先アグリーメントを構成することによって実行されます。 アグリーメントには、両方の取引先の特定のビジネス プロファイルから、共通する双方向のメッセージ処理プロパティがまとめられます。 アグリーメントは、各ビジネス プロファイルに対して定義されたプロトコル設定に基づいて作成されます。 2 つのビジネス プロファイル間に取引先アグリーメントを実装するには、メッセージを交換する各ビジネス プロファイルのプロパティを定義します。 取引先管理 (TPM) ユーザー インターフェイスで、AS2 メッセージ受信者と AS2 メッセージ送信者として各ビジネス プロファイルのプロパティを設定します。 TPM の画面はでは、**パーティ**のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、開発者でなくても AS2 処理を構成できます。  
  
 AS2 プロパティは、ビジネス プロファイルの「トランスポート プロトコル設定」の一部として、または取引先アグリーメントに AS2 設定を直接指定することによって、指定できます。 プロトコル設定の詳細については、[プロトコル設定](../core/protocol-settings.md)を参照してください。 契約の詳細については、[取引先アグリーメント](../core/trading-partner-agreement.md)を参照してください。  次の AS2 機能を構成するには、AS2 固有のプロパティを設定します。  
  
- 否認不可ストレージ オプションの選択  
  
- 送信メッセージの署名、圧縮、または暗号化の各プロパティの指定  
  
- 送信メッセージの MDN の要求  
  
- AS2 メッセージのヘッダーで署名、圧縮、暗号化、および MDN の各プロパティをオーバーライドすることによる着信 MDN のプロパティの設定  
  
  詳細については、どの取引先のパートナー アグリーメント AS2 処理に役立つ、[AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md)を参照してください。  
  
> [!NOTE]
>  EDI 処理と異なり、AS2 処理にはグローバル プロパティはありません。  
  
## <a name="as2-receive-side-processing"></a>受信側の AS2 処理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で AS2 メッセージを受信すると、AS2 受信パイプラインでメッセージが処理されます。 AS2 (AS2EdiReceive) 経由で EDI メッセージを受信するパイプラインがあり、AS2 処理と EDI 処理の両方が実行されます。 もう 1 つのパイプライン (AS2Receive) は、AS2 経由で受信した非 EDI メッセージの AS2 処理のみを行います。  
  
 受信側の AS2 処理には、次のものが含まれます。  
  
- 取引先アグリーメント参照  
  
  > [!NOTE]
  >  以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティの定義にアグリーメントの定義も含まれていました。 そのため、受信パイプラインがパーティのプロパティを検索する場合は、パーティの定義内でアグリーメント定義を内部的に検索してから、必要に応じてメッセージを処理します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティ (取引先) は取引先アグリーメントとは異なるため、取引先アグリーメントだけが検索されます。  
  > 
  > [!NOTE]
  >  メッセージが解決されるすべてのアグリーメントが無効になっている場合、メッセージは中断されます。  また、イベント ログに警告が記録されます。  
  
- 否認不可データベースへのメッセージのコピーの保存  
  
- 重複メッセージの確認  
  
- 複数のドキュメントを含むメッセージの処理  
  
- MIME エンベロープからのドキュメント ファイル名の取得  
  
- メッセージの解読  
  
- メッセージの圧縮解除  
  
- メッセージのデジタル署名の検証  
  
- HTTP 応答の生成  
  
- MDN 応答の生成  
  
  受信側の AS2 処理を使用する場合は、次の点を考慮する必要があります。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、同期モードまたは非同期モードで MDN を返します。 MDN が非同期に返される場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は別の送信ポートを経由して MDN を送信する必要があります。  
  
- 非 EDI ファイル (XML 以外) を AS2 経由で受信し、非 EDI ペイロードの逆アセンブリを実行する必要がある場合、2 番目の受信パイプラインでループバック メカニズムを使用する必要があります。 詳細については、[AS2 経由で受信した非 EDI メッセージの受信側の処理](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md)を参照してください。  
  
- 受信場所は HTTP アダプターのみ使用できます。  
  
- 受信側の AS2 処理の詳細については、[どのように BizTalk Server 受信 AS2 メッセージ](../core/how-biztalk-server-receives-as2-messages.md)を参照してください。  
  
- 受信パイプラインで AS2 逆アセンブラーによって実行される特定の処理の詳細については、[受信 AS2 メッセージの処理](../core/processing-an-incoming-as2-message.md)を参照してください。  
  
## <a name="as2-send-side-processing"></a>送信側の AS2 処理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送信 AS2 メッセージを生成および送信すると、AS2 送信パイプラインでメッセージが処理されます。 AS2 (AS2EdiSend) 経由で EDI メッセージを送信するパイプラインがあり、AS2 処理と EDI 処理の両方が実行されます。 もう 1 つのパイプライン (AS2Send) は、AS2 経由で送信された非 EDI メッセージの AS2 処理のみを行います。  
  
 送信側の AS2 処理には、次のものが含まれます。  
  
- 取引先アグリーメント参照  
  
  > [!NOTE]
  >  以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティの定義にアグリーメントの定義も含まれていました。 そのため、送信パイプラインがパーティのプロパティを検索する場合は、パーティの定義内でアグリーメント定義を内部的に検索してから、必要に応じてメッセージを処理します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パーティ (または取引先パートナー) は具体的には、次のように取引先パートナー アグリーメントの取引先アグリーメントの送信パイプラインは異なりますがあるため、します。  
  > 
  > [!NOTE]
  >  メッセージが解決されるすべてのアグリーメントが無効になっている場合、メッセージは中断されます。  また、イベント ログに警告が記録されます。  
  
- 否認不可データベースへのメッセージのコピーの保存  
  
- AS2 エンベロープの適用  
  
- 複数のドキュメントの送信  
  
- MIME エンベロープの一部としての各ドキュメント ファイル名のソート  
  
- メッセージへの署名  
  
  > [!NOTE]
  >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、既定の署名証明書をオーバーライドし、アグリーメントで合意した証明書を代わりに使用することができます。 既定の送信メッセージの署名証明書をオーバーライドする方法の詳細については、[AS2 プロパティを設定する](../core/configuring-as2-properties.md)を参照してください。  
  
- メッセージの圧縮  
  
- メッセージの暗号化  
  
- MDN の MIC 値の計算  
  
- 着信 MDN の処理 (同期 MDN の場合)  
  
- メッセージの再送信 (MDN が受信されない場合)  
  
  受信側の AS2 処理を使用する場合は、次の点を考慮する必要があります。  
  
- 送信ポートは HTTP アダプターのみ使用できます。  
  
- 送信側の AS2 処理の詳細については、[どのように BizTalk Server 送信 AS2 メッセージ](../core/how-biztalk-server-sends-as2-messages.md)を参照してください。  
  
- 送信パイプラインで実行される特定の処理の詳細については、[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md)   
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)   
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)