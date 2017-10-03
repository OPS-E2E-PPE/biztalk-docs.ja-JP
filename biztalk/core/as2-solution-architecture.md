---
title: "AS2 ソリューションのアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22557059bd13dd99e0b24a2291b7f121d561bbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="as2-solution-architecture"></a>AS2 ソリューション アーキテクチャ
AS2 処理は EDI 処理とは別個に実行されます。 AS2 メッセージの受信、処理、受信確認の送信は EDI ペイロードの処理とは別個に行われます。 したがって、AS2 処理は EDI 処理とは別個に設計され、構成されています。 また、AS2 を使用して、EDI メッセージまたは非 EDI メッセージのどちらかを転送することができます。  
  
 このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のエンド ツー エンド、受信側、および送信側の処理を含む AS2 ソリューションのアーキテクチャについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [AS2 メッセージング](../core/as2-messaging.md)  
  
-   [AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)