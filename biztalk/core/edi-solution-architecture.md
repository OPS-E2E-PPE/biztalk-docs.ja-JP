---
title: EDI ソリューションのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c4ce03c9188a03b47cc2fbe3f67a8be163acdc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009979"
---
# <a name="edi-solution-architecture"></a>EDI ソリューションのアーキテクチャ
電子データ交換 (EDI) は、ビジネス エンティティがデータを電子的に交換するために最も広く使用されている方法の 1 つです。 EDI を使用するには、メッセージの構文や標準 (ANSI X12、UN/EDIFACT など)、メッセージング プロトコル、およびトランスポートが必要です。 EDI によるメッセージングには、次のような特性があります。  
  
- EDI のメッセージング プロトコルにより、データが常に期待どおりに配信され、破損したデータや正しくないデータが自動的に検出および報告されるようにすることができます。  
  
- EDI のメカニズムでは、通常、データ集計スキーマ (バッチ処理) が指定されています。  
  
- EDI ガイドラインのサブセットや特定の実装を組み込むことにより、EDI のドキュメント定義をカスタマイズできます。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、EDI メッセージの解析とシリアル化を実行できる EDI 専用の受信パイプラインと送信パイプラインを使用して EDI メッセージを処理します。 このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における EDI ソリューションのアーキテクチャ (受信側および送信側の処理に関する詳細、メッセージの検証、状態レポートなど) について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI メッセージング](../core/edi-messaging.md)  
  
-   [EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [EDI メッセージの検証](../core/edi-message-validation.md)  
  
-   [XML ツール拡張機能の使用](../core/using-the-xml-tool-extensions.md)