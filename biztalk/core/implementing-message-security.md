---
title: メッセージ セキュリティの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971977a0-b74e-4408-8a07-ad327658f2bc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a2b31f73340db43d84f1a2d643c6fc651e3c940
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332379"
---
# <a name="implementing-message-security"></a>メッセージ セキュリティの実装
署名および暗号化されたメッセージの送受信に証明書を使用するように Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を構成できます。 BizTalk Server では、暗号化およびデジタル署名用の証明書を使用することで次の処理が可能になります。  
  
- 信頼できるデータを送受信できます。  
  
- 処理するデータの安全性を確保できます。  
  
- 承認されたパーティにメッセージを確実に送信できます。  
  
- 承認されたパーティからメッセージを確実に受信できます。  
  
  ここでは、BizTalk Server パイプライン、受信場所、ポート、および BizTalk Server 環境を構成してメッセージ セキュリティを実装する方法について説明します。  
  
  メッセージ セキュリティの詳細については、次を参照してください。[メッセージ セキュリティの計画](../core/planning-message-security.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [暗号化されたメッセージの送受信](../core/sending-and-receiving-encrypted-messages.md)  
  
-   [署名付きメッセージの送受信](../core/sending-and-receiving-signed-messages.md)  
  
-   [パーティの解決での証明書の使用](../core/using-certificates-for-party-resolution.md)