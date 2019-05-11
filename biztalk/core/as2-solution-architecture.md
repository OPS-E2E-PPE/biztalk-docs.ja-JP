---
title: AS2 ソリューションのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f25fb229a37896846f81e37c3cc71e8419d854
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528854"
---
# <a name="as2-solution-architecture"></a>AS2 ソリューション アーキテクチャ
AS2 処理は EDI から個別に実行を処理します。 AS2 メッセージを受信、処理、および EDI ペイロードの処理とは別に受信確認の送信。 結果として、AS2 処理が設計し、EDI 処理とは別に構成されています。 さらに、AS2 を使用して EDI メッセージまたは非 EDI メッセージを転送することができます。  
  
 このセクションで AS2 ソリューションのアーキテクチャを説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンド ツー エンド、受信側、送信側など、処理します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [AS2 メッセージング](../core/as2-messaging.md)  
  
-   [AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)