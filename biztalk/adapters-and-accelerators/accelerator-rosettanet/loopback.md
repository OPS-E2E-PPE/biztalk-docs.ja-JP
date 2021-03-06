---
title: Loopback |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, 0A1 agreements
- loopbacks, running
- loopbacks, 0A1 agreements
- loopbacks, about loopbacks
- loopbacks, 0A1 messages
- agreements, loopback agreements
- messages, 0A1 messages
- loopbacks
- Loopback utility
- loopbacks, syntax
- 0A1 messages
- loopbacks, Loopback utility
- syntax [loopbacks]
- agreements, Loopback utility
ms.assetid: b4ebbdac-05be-4dfc-a133-6b752994e85a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1cc2a6c1434812f876ea71881890a08d165f471
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283310"
---
# <a name="loopback"></a>Loopback
home-to-partner アグリーメントのミラー コピーであるループバック アグリーメントが自動的に生成されるようにするには、ループバック ユーティリティを使用します。 このユーティリティを使用すると、1 台のコンピューターで home-to-partner と partner-to-home のメッセージ交換を実行できます。 このユーティリティは、0A1 メッセージの有無にかかわらず使用できます。 ループバック アグリーメントは、アクション メッセージ (非 0A1) アグリーメントと 0A1 アグリーメントのどちらに対しても作成できます。  

 このユーティリティは、ホーム組織を送信者のロールに登録したり、登録を解除したりするためにも使用できます。 ホーム組織を有効にするユーティリティを使用すると、2 つの送信ポートを作成します。\<ホーム\>します。非同期と\<ホーム\>します。組織が、パートナーとの通信に使用する同期します。  

## <a name="location-in-sdk"></a>SDK でのパス  
 \<*drive*\>\ Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\  

## <a name="running-loopback"></a>ループバックの実行  

#### <a name="to-run-loopback"></a>ループバックを実行するには  

1.  コマンド プロンプトを開きます。  

2.  移動\<*ドライブ*\>\ Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。  

3.  コマンド プロンプトで「 **Loopback**と、必須および適切なスイッチを入力し、ENTER キーを押します。  

## <a name="syntax-for-loopback"></a>ループバックの構文  
 次に、このコマンドライン ユーティリティを起動するために使用する構文を示します。  

```  
Loopback [/enable|/disable <home_organization>] [/mirror|/unmirror <agreement_name>] [/NoF <0A1_agreement>]  
```  

## <a name="syntax-description"></a>構文の説明  
 次の表で、ループバック ユーティリティが使用する構文の各要素について説明します。  

|**構文**|**[説明]**|  
|----------------|---------------------|  
|**enable**|<home_organization> で指定された組織を送信者ロールとして登録します。 2 つの送信ポートを作成します\<ホーム\>します。非同期と\<ホーム\>します。ホーム組織への通信を使用して、パートナーを同期します。|  
|**disable**|送信者ロールとしてのホーム組織の登録を解除します。|  
|**home_organization**|送信者ロールとして登録する (または登録解除する) 組織。|  
|**mirror**|指定されたアグリーメントに基づいてループバック アグリーメントを作成します。 \< **agreement_name**\>します。|  
|**unmirror**|指定されたアグリーメントに基づいてループバック アグリーメントを削除します。 \< **agreement_name\>** します。|  
|**agreement_name**|ループバック シナリオでミラー化または非ミラー化するアグリーメント。|  
|**NoF**|セット、 **0A1 アグリーメント**Loopback ユーティリティによってミラー化されたアクション メッセージ アグリーメントのプロパティ\<0A1_agreement\>します。 A **/NoF**のみが含まれている Loopback コマンドにスイッチを追加できます、 **ミラー/** スイッチします。|  
|**0A1_agreement**|agreement_name のミラー アグリーメントによって使用される 0A1 アグリーメント。 このアグリーメントは、応答側 0A1 アグリーメントをミラー化することによって生成されます。|  

## <a name="remarks"></a>コメント  
 ループバック ユーティリティは、ループバック アグリーメントの作成におけるロールを切り替えます。 ループバック ユーティリティを実行すると、元のアグリーメントのホーム組織は、ループバック アグリーメントでは取引先組織になります。 同様に、元のアグリーメントの取引先組織は、ループバック アグリーメントではホーム組織になります。 ループバック ユーティリティは、ホーム ロール プロパティの設定も切り替えます。 このユーティリティを実行すると、元のアグリーメントで開始側だったホーム ロール プロパティは応答側になり、応答側だったホーム ロール プロパティは開始側になります。 その他のプロパティはどれも変化しません。  

 ループバック ユーティリティでは、ループバック アグリーメントに元のアグリーメントと同じ名前が付けられ、先頭に "loopback:" が追加されます。 混乱を防ぐため、"loopback" で始まる名前をアグリーメントに付けないでください。  

 ループバック アグリーメントを既に生成してあるアグリーメントに対してこのユーティリティを実行すると、既存のループバック アグリーメントが非ミラー化され、新しいループバック アグリーメントが作成されます。  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールではミラー化されたアグリーメントを作成できないので、ループバック ユーティリティが必要です。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールでは、ホーム組織、取引先組織、およびホーム ロールのプロパティが元に戻され、その他すべてのフィールドが既存のアグリーメントのフィールドと同一であるアグリーメントを作成できません。 同様に、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、ループバック アグリーメントをコンソールで直接変更できません。 ループバック アグリーメントをコンソールで開こうとすると、エラーが返されます。 ループバック アグリーメントを変更する必要がある場合は、元のアグリーメントを変更してから、元のアグリーメントに対してループバック ユーティリティを再び実行し、ループバック アグリーメントを再生成します。  

> [!IMPORTANT]
>  このループバック シナリオでは、署名付きアグリーメントはサポートされません。 このシナリオでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] で署名証明書を使用して設定できるパーティは 1 つだけなので、署名付きメッセージは検証に失敗します。 ホーム組織と取引先組織が同じ署名証明書を使用することはできません。 これは、署名証明書を使用してパーティを一意に識別することに関連した [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] の制約です。 そのため、2 つの BizTalk パーティが同じ証明書を共有することはできません。  

 ループバック実装の詳細については、次を参照してください。 [Loopback チュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)します。  

## <a name="using-loopback-with-0a1-agreements"></a>ループバックと 0A1 アグリーメントの使用  
 0A1 (障害通知) メッセージを生成するようにループバック シナリオを設定できます。 これを行うには、要求アクション メッセージ アグリーメント、開始側 0A1 アグリーメント、および応答側 0A1 アグリーメントをホーム組織用に作成する必要があります。 次に、これらの各アグリーメントに対してループバック ユーティリティを実行し、応答アクション メッセージ アグリーメント、開始側 0A1 アグリーメント、および応答側 0A1 アグリーメントを取引先組織用に作成する必要があります。 これが必要なのは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用してこれらのアグリーメントを作成できないからです。  

 アグリーメント一式には、次のメッセージのアグリーメントが含まれている必要があります。 説明しやすいように、アクション メッセージは 3A4 とします。  

-   Home_to_Partner_3A4 (アクション メッセージ) アグリーメント。 HOME 組織から PARTNER 組織へのアクション メッセージ PIP を開始するためのアグリーメント。  

-   Home_to_Partner_Initiator_0A1 アグリーメント。 HOME 組織から PARTNER 組織への PIP 0A1 を開始するためのアグリーメント。  

-   Home_to_Partner_Responder_0A1 アグリーメント。 PARTNER 組織から HOME 組織への PIP 0A1 を受信するためのアグリーメント。  

-   Loopback:Home_to_Partner_3A4 (応答メッセージ) アグリーメント。 HOME 組織から PARTNER 組織への PIP 3A4 を受信するためのアグリーメント。  

-   Loopback:Home_to_Partner_Responder_0A1 アグリーメント。 PARTNER 組織から HOME 組織への PIP 0A1 を開始するためのアグリーメント。  

-   Loopback:Home_to_Partner_Initiator_0A1。 HOME 組織から PARTNER 組織への PIP 0A1 を受信するためのアグリーメント。  

## <a name="creating-the-loopback-agreements-for-0a1-messages"></a>0A1 メッセージ向けのループバック アグリーメントの作成  
 アグリーメント一式を作成するには、ループバック ユーティリティを使用して、取引先に関するアクション メッセージ アグリーメントと 0A1 アグリーメントを作成する必要があります。 次の表に、取引先のループバック アグリーメントを生成するために必要なループバック操作を示します。 説明しやすいように、このトピックの表では 3A4 メッセージを使用します。  

|手順|HOME アグリーメント|  
|----------|---------------------|  
|1, 4|Home_to_Partner_3A4<br /><br /> ホーム組織:Home<br /><br /> パートナー組織:PARTNER<br /><br /> ホーム組織のロール。Initiator<br /><br /> 0A1 アグリーメント:Home_to_Partner_Initiator_0A1<br /><br /> 説明:HOME から PARTNER への PIP 3A4 を開始するためのアグリーメント|  
|2|Home_to_Partner_Initiator_0A1<br /><br /> ホーム:ホーム (Home)<br /><br /> パートナー:Partner<br /><br /> ロール:Initiator<br /><br /> 説明:HOME から PARTNER への PIP 0A1 を開始するためのアグリーメント|  
|3|Home_to_Partner_Responder_0A1<br /><br /> ホーム:ホーム (Home)<br /><br /> パートナー:Partner<br /><br /> ロール:応答側<br /><br /> 説明:パートナーから HOME への PIP 0A1 を受信するためのアグリーメント|  

|手順|PARTNER アグリーメント (Loopback.exe を使用したミラー化)|  
|----------|--------------------------------------------------------|  
|7|Loopback:Home_to_Partner_3A4<br /><br /> ホーム:Partner<br /><br /> パートナー:ホーム (Home)<br /><br /> ロール:応答側<br /><br /> 0A1 アグリーメント:Loopback:Home_to_Partner_Responder_0A1<br /><br /> 説明:ホームから PARTNER への PIP 3A4 を受信するためのアグリーメント<br /><br /> Loopback コマンドを作成すること。Loopback /mirror Home_to_Partner_3A4 /NoF Loopback:Home_to_Partner_Responder_0A1|  
|5|Loopback:Home_to_Partner_Responder_0A1<br /><br /> ホーム:Partner<br /><br /> パートナー:ホーム (Home)<br /><br /> ロール:Initiator<br /><br /> 説明:PARTNER から HOME への PIP 0A1 を開始するためのアグリーメント<br /><br /> Loopback コマンドを作成すること。Loopback/mirror Home_to_Partner_Responder_0A1|  
|6|Loopback:Home_to_Partner_Initiator_0A1<br /><br /> ホーム:Partner<br /><br /> パートナー:ホーム (Home)<br /><br /> ロール:応答側<br /><br /> 説明:ホームから PARTNER への PIP 0A1 を受信するためのアグリーメント<br /><br /> Loopback コマンドを作成すること。Loopback /mirror Home_to_Partner_Initiator_0A1|  

 これらの表に示したループバック コマンドは、次の手順の一部として実行します。  

#### <a name="to-create-the-agreements-for-a-loopback-scenario-using-0a1-messages"></a>0A1 メッセージを使用してループバック シナリオのアグリーメントを作成するには  

1. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで、ホーム組織によって送信される要求アクション メッセージのアグリーメントを作成します。  

2. ホーム組織によって送信される開始側 0A1 メッセージのアグリーメントを作成し、次の操作を行います。  


   |         プロパティ         |                  目的                  |
   |--------------------------|----------------------------------------------|
   |   **自分の所属組織**    |        ホーム組織に設定します。         |
   | **取引先組織** |             取引先に設定します。              |
   |      **ホーム ロール**       | 設定**PIP Failure Notifier (開始側)** します。 |


3. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用して、ホーム組織に送信する応答側 0A1 メッセージのアグリーメントを作成し、次の操作を行います。  


   |         プロパティ         |                      目的                      |
   |--------------------------|------------------------------------------------------|
   |   **自分の所属組織**    |            ホーム組織に設定します。             |
   | **取引先組織** |                 取引先に設定します。                  |
   |      **ホーム ロール**       | 設定**Failure Report Administrator (応答側)** します。 |


4. 使用して[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールで、設定、 **0A1 アグリーメント**ホーム組織の開始側 0A1 アグリーメントの名前に、ホーム組織の要求アクション メッセージ アグリーメントのプロパティ。  

5. ループバック ユーティリティを使用して、取引先組織によって送信される開始側 0A1 メッセージのアグリーメントを作成します。 これを行うには、ホーム組織の応答側 0A1 アグリーメントをミラー化します。 新しい 0A1 アグリーメントでは、名前作成**ループバック:\<0A1 アグリーメント名\>** します。 `My organization`プロパティが、パートナー、`Partner organization`プロパティが、ホーム組織と`Home role`プロパティは**PIP Failure Notifier (開始側)**。  

6. ループバック ユーティリティを使用して、取引先組織の応答側 0A1 メッセージのアグリーメントを作成します。 これを行うには、ホーム組織の開始側 0A1 アグリーメントをミラー化します。 新しい 0A1 アグリーメントでは、名前作成**ループバック:\<0A1 アグリーメント名\>** します。 `My organization`プロパティが、パートナー、`Partner organization`プロパティが、ホーム組織と`Home role`プロパティは**Failure Report Administrator (応答側)**。  

7. ループバック ユーティリティを使用して、取引先組織の応答アクション メッセージのアグリーメントを作成します。 同じコマンドで、[0A1 アグリーメント] プロパティを取引先の応答側 0A1 アグリーメントに設定する必要があります。 ホーム組織の要求アクション メッセージ アグリーメントをミラー化を使用してこれを行う、 **/NoF**スイッチとパートナーの応答側 0A1 アグリーメントの名前。 新しい応答アクション メッセージ アグリーメントでは、名前作成**Loopback:\<契約名\>** します。 `My organization` プロパティは取引先に設定され、"0A1 アグリーメント" プロパティは取引先の応答側 0A1 アグリーメントに設定されます。  

## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [ループバックのチュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
