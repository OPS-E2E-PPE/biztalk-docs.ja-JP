---
title: メッセージ コンテキスト プロパティ Values1 を割り当てる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e76c62-3110-482c-8083-84d411e6f475
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9f5a42e208d81f8898ce85592402f675d1b361
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979743"
---
# <a name="how-to-assign-message-context-property-values"></a>メッセージ コンテキスト プロパティの値を割り当てる方法
BizTalk オーケストレーションから JD Edwards EnterpriseOne アダプター接続セッションを管理するには、Microsoft.BizTalk.Adapters.JDEProperties.dll への参照をプロジェクトに追加する必要があります。 このアセンブリは、%SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin に配置されています。  
  
 このプロパティ スキーマを参照すると、オーケストレーション デザイナのメッセージの割り当て図形など、さまざまな BizTalk 開発ツールで、追加のコンテキスト プロパティにアクセスできるようになります。  
  
 コンテキスト プロパティにアクセスするには、JD Edwards EnterpriseOne 名前空間で使用できるコンテキスト プロパティのうちいずれかを指定します。 Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で構文 Message(JDE.Property) を使用します。 プロパティの一覧については、JD Edwards EnterpriseOne アダプター セッション管理に関する説明を参照してください。  
  
 BizTalk では、メッセージを変更できません。  
  
### <a name="to-assign-context-property-value"></a>コンテキスト プロパティ値を割り当てるには  
  
1. 新しいメッセージを作成します。  
  
2. メッセージのコンテンツを設定します (既存のメッセージを割り当てるなど)。  
  
3. プロパティを設定します。  
  
   Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされた送信ポートに送信するメッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。 次に、JD Edwards EnterpriseOne 名前空間の使用可能ないずれかのコンテキスト プロパティを指定します。  
  
   次の構文 `Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties1.md)   
 [セッション管理について](../core/about-session-management2.md)   
 [チュートリアル: BizTalk Adapter for JD Edwards EnterpriseOne の使用](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)