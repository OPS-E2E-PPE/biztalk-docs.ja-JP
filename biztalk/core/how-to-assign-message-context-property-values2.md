---
title: メッセージ コンテキスト プロパティ Values2 に割り当てる方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 8f0e19a425a4842e3bfac150d1cac851e4686f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247210"
---
# <a name="how-to-assign-message-context-property-values"></a>メッセージ コンテキスト プロパティの値を割り当てる方法
BizTalk オーケストレーションから JD Edwards OneWorld 接続セッションを管理するには、プロジェクトの Microsoft.BizTalk.Adapters.JDEProperties.dll に参照を追加する必要があります。 このアセンブリは、%SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin に配置されています。  
  
 このプロパティ スキーマを参照すると、オーケストレーション デザイナのメッセージの割り当て図形など、さまざまな BizTalk 開発ツールで、追加のコンテキスト プロパティにアクセスできるようになります。  
  
 コンテキスト プロパティにアクセスするには、JD Edwards OneWorld 名前空間で使用できるプロパティのうちいずれかを指定します。 Microsoft BizTalk Adapter for JD Edwards OneWorld にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で構文 Message(JDE.Property) を使用します。 プロパティの一覧については、JD Edwards OneWorld セッション管理に関する説明を参照してください。  
  
 BizTalk では、メッセージを変更できません。  
  
### <a name="to-assign-a-message-context-property-value"></a>メッセージ コンテキストのプロパティ値を割り当てるには  
  
1.  新しいメッセージを作成します。  
  
2.  メッセージのコンテンツを設定します (既存のメッセージを割り当てるなど)。  
  
3.  プロパティを設定します。  
  
 Microsoft BizTalk Adapter for JD Edwards OneWorld にバインドされた送信ポートに送信するメッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。 次に、JD Edwards OneWorld 名前空間の使用可能ないずれかのコンテキスト プロパティを指定します。  
  
 構文です。`Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties2.md)   
 [セッション管理について](../core/about-session-management1.md)   
 [チュートリアル: BizTalk アダプターを使用して JD Edwards OneWorld の](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)