---
title: メッセージ コンテキスト プロパティ Values2 を割り当てる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137f82ab-f301-465d-be78-a6e67971dd3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 083fa3e8d6474e0f369cc1c66210ac39f4e1d56e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342700"
---
# <a name="how-to-assign-message-context-property-values"></a>メッセージ コンテキスト プロパティの値を割り当てる方法
を BizTalk オーケストレーションから JD Edwards OneWorld 接続セッションを管理するには、プロジェクトの Microsoft.BizTalk.Adapters.JDEProperties.dll に参照を追加する必要があります。 このアセンブリは %systemdrive%\program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin にあります。  
  
 このプロパティ スキーマを参照すると後、は、追加のコンテキスト プロパティをさまざまな BizTalk 開発ツール、たとえば、メッセージの割り当て図形をオーケストレーション デザイナー内でアクセスできます。  
  
 コンテキスト プロパティにアクセスするには、JD Edwards OneWorld 名前空間内で使用できるプロパティのいずれかを指定します。 Microsoft BizTalk Adapter for JD Edwards OneWorld にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取りは、メッセージ (JDE の構文を使用します。プロパティの場合)、式で。 プロパティの一覧については、JD Edwards OneWorld セッション管理を参照してください。  
  
 BizTalk メッセージは変更できません。  
  
### <a name="to-assign-a-message-context-property-value"></a>メッセージ コンテキスト プロパティの値を割り当てる  
  
1. 新しいメッセージを作成します。  
  
2. コンテンツの設定、メッセージなどの既存のメッセージを割り当てます。  
  
3. プロパティを設定します。  
  
   Microsoft BizTalk Adapter for JD Edwards OneWorld にバインドされている送信ポートに送信メッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。 次に、JD Edwards OneWorld 名前空間内で使用できるプロパティのいずれかを指定します。  
  
   次の構文 `Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties2.md)   
 [セッション管理について](../core/about-session-management1.md)   
 [チュートリアル: BizTalk Adapter for JD Edwards OneWorld の使用](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)