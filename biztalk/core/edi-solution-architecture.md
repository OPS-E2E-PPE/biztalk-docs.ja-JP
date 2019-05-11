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
ms.openlocfilehash: 9df4d308af97e0fcccf52d2c6f42660afa7cf079
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350252"
---
# <a name="edi-solution-architecture"></a>EDI ソリューションのアーキテクチャ
電子データ交換 (EDI) では、ビジネス エンティティ データ交換を電子的に最も一般的な手段の 1 つです。 メッセージの構文や標準 (ANSI X12、UN/EDIFACT など)、メッセージング プロトコル、およびトランスポート EDI を使用する必要があります。 次に、EDI メッセージングの特性を示します。  
  
- データは、常に、想定どおりに到着して破損しているか正しくないデータが自動的に検出され、報告される EDI メッセージング プロトコルを確認します。  
  
- EDI のメカニズムは、通常、データ集計のスキーマ (バッチ処理) を指定します。  
  
- ユーザーは、プロパティのサブセットまたは EDI ガイドラインの特定の実装を実装することで多くの場合、EDI ドキュメント定義をカスタマイズします。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用して EDI メッセージを処理では、受信し、解析と EDI メッセージをシリアル化を実行できる EDI 送信パイプラインを特定します。 このセクションでの EDI ソリューションのアーキテクチャを説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、受信側と送信側の処理、メッセージの検証、および状態レポートの詳細を含めています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI メッセージング](../core/edi-messaging.md)  
  
-   [EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [EDI メッセージの検証](../core/edi-message-validation.md)  
  
-   [XML ツール拡張機能の使用](../core/using-the-xml-tool-extensions.md)