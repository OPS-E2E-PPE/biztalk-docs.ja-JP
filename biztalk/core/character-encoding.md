---
title: 文字エン コード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 319ddd649e47e053fe2896d577f28b72602593e3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014681"
---
# <a name="character-encoding"></a>Character Encoding
TIBCO Enterprise Message Service (EMS) は、TIBCO EMS 用の BizTalk アダプタで EMS に送信されるメッセージでのさまざまな文字エンコードをサポートします。 メッセージは、既定の UTF-8 エンコードを使用してエンコードされます。 メッセージを受信すると、アダプターはメッセージのエンコードを判断し、該当する文字列を UTF-8 に変換した後で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを渡します。 すべての文字変換に Microsoft .NET Framework のクラスが使用されます。そのため、アダプタは Microsoft .NET Framework に用意されている文字変換をサポートします。  
  
## <a name="running-in-a-clustered-environment"></a>クラスタ環境での実行  
 キューに公開されたメッセージは、EMS サーバーにあらかじめ定義された順序で、コンシューマーによって処理されます。このとき、クラスター化された [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境内で 1 つのアダプターのみがメッセージを受信します。 キューとして構成することができます*排他*です。 これは、キューのメッセージ処理に対して最初に登録したアダプタのみが、メッセージを受信することを意味します。 EMS サーバーは、排他的コンシューマがメッセージの受信を確認しない場合にのみ、他のコンシューマにメッセージを送信します。 排他的なキューは EMS 構成で構成され、クライアントでは構成できません。  
  
> [!NOTE]
>  トピックのサブスクリプションについて: ためのすべてのアダプター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループが同じように構成されている、すべてのメッセージのサブスクライブされたおよびそれぞれのトピック サブスクリプションはメッセージを受信します。  
  
## <a name="transaction-support"></a>トランザクションのサポート  
 アダプタは、オーケストレーションの送信ポートで必要になったときに、トランザクションに対するサポートを提供します。 アダプターがメッセージを待機している間は、EMS サーバーでのトランザクションのサポートは行われません。ただし、メッセージが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に正常に送信された後は、EMS からのすべてのメッセージの受信がアダプターによって確認されます。 EMS は、未確認のメッセージをアダプタに再送します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for TIBCO EMS のセキュリティ](../core/security-in-biztalk-adapter-for-tibco-ems.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)