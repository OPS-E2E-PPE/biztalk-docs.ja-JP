---
title: メッセージ コンテキスト プロパティ Values1 に割り当てる方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 39bb2a4c6520c1ff3a21889e7508bb2cf417b817
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247306"
---
# <a name="how-to-assign-message-context-property-values"></a>メッセージ コンテキスト プロパティの値を割り当てる方法
BizTalk オーケストレーションから JD Edwards EnterpriseOne アダプター接続セッションを管理するには、Microsoft.BizTalk.Adapters.JDEProperties.dll への参照をプロジェクトに追加する必要があります。 このアセンブリは、%SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin に配置されています。  
  
 このプロパティ スキーマを参照すると、オーケストレーション デザイナのメッセージの割り当て図形など、さまざまな BizTalk 開発ツールで、追加のコンテキスト プロパティにアクセスできるようになります。  
  
 コンテキスト プロパティにアクセスするには、JD Edwards EnterpriseOne 名前空間で使用できるコンテキスト プロパティのうちいずれかを指定します。 Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で構文 Message(JDE.Property) を使用します。 プロパティの一覧については、JD Edwards EnterpriseOne アダプター セッション管理に関する説明を参照してください。  
  
 BizTalk では、メッセージを変更できません。  
  
### <a name="to-assign-context-property-value"></a>コンテキスト プロパティ値を割り当てるには  
  
1.  新しいメッセージを作成します。  
  
2.  メッセージのコンテンツを設定します (既存のメッセージを割り当てるなど)。  
  
3.  プロパティを設定します。  
  
 Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされた送信ポートに送信するメッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。 次に、JD Edwards EnterpriseOne 名前空間の使用可能ないずれかのコンテキスト プロパティを指定します。  
  
 構文です。`Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties1.md)   
 [セッション管理について](../core/about-session-management2.md)   
 [チュートリアル: BizTalk アダプターを使用して JD Edwards EnterpriseOne の](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)