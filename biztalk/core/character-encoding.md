---
title: 文字エン コード |Microsoft Docs
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
ms.openlocfilehash: 7418a6e6d1321450e0156fedc38fb5cb69a260e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357468"
---
# <a name="character-encoding"></a>Character Encoding
TIBCO Enterprise Message Service (EMS) は、TIBCO EMS 用に BizTalk アダプタで EMS に送信されるメッセージで別の文字のエンコードをサポートします。 メッセージは、既定の utf-8 エンコーディングを使用してエンコードされます。 アダプターがメッセージのエンコードを判断し、メッセージを指定する前に、適切な文字列を utf-8 に変換メッセージを受信するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 すべての文字変換を使用して、Microsoft .NET Framework クラスです。そのため、アダプターでは、この同じフレームワークによって提供される、文字変換をサポートしています。  
  
## <a name="running-in-a-clustered-environment"></a>クラスター化された環境で実行されています。  
 キューに公開されたメッセージは、EMS サーバーで事前定義された順序で、コンシューマーによって使用される-で、クラスター化されたアダプターを 1 つだけ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境は、メッセージを受信します。 キューとして構成できる*排他*します。 つまり、キューにメッセージの消費量の自分自身を登録する最初のアダプターのみがメッセージを受信します。 EMS サーバーは、排他的コンシューマがメッセージの受信を確認していない場合のみメッセージと他のコンシューマーに送信します。 排他的なキューの構成は EMS 構成で実行され、構成可能なクライアントではありません。  
  
> [!NOTE]
>  トピックのサブスクリプションについて: ためのすべてのアダプターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループが同じように構成されている、すべてのメッセージのサブスクライブ、およびそれぞれのトピック サブスクリプションはメッセージを受信します。  
  
## <a name="transaction-support"></a>トランザクションのサポート  
 アダプターは、オーケストレーションの送信ポートで必要なときに、トランザクションのサポートを提供します。 アダプターがメッセージをリッスンしている場合、トランザクションのサポート、EMS サーバーではありません。ただし、アダプターでに正常に送信された後、EMS からのすべてのメッセージの受信確認される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 EMS では、アダプターに未確認のメッセージを再送信します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for TIBCO EMS のセキュリティ](../core/security-in-biztalk-adapter-for-tibco-ems.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)