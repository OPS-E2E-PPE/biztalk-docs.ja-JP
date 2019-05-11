---
title: Web Services2 を公開するための計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, planning
- virtual directories, updating
- BizTalk Server Web Services Publishing Wizard
ms.assetid: 69107557-48e2-4f15-ba42-9fad476a8294
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1223dbb434df74728b3f7fe9b21dcecdc5378ba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395669"
---
# <a name="planning-for-publishing-web-services"></a>Web サービス公開の計画
Web サービスは、オーケストレーション内からアクセスできます。 Web サービスを発行するのに、BizTalk Web サービス公開ウィザードを使用することもできます。  
  
 次の表では、Web サービスの計画で検討する必要がある質問の一部を示します。  
  
|計画段階の考慮事項|推奨|  
|-----------------------|--------------------|  
|BizTalk Server プロジェクトをビルドしたでしょうか。|BizTalk Web サービス公開ウィザードを実行する前に BizTalk Server プロジェクトをビルドする必要があります。|  
|Web サービスを実行するシステムを有効にしますか。|BizTalk Web サービス公開ウィザードを実行する前にコンピューターで Web サービスを有効にする必要があります。 Web サービスには、システムを有効にする方法の詳細については、次を参照してください。 [Web サービスを有効にする](../core/enabling-web-services.md)します。|  
|有効な XML 文字とのみの要素がスキーマに含まれているでしょうか。|Web サービスは、中国語、日本語、韓国語 (CJK) 統合漢字拡張 A 文字をサポートしていません。 特定の XML スキーマ (XSD) 要素の制限もあります。 有効な XML 文字とサポートされている要素および要素に関する考慮事項の詳細については、次を参照してください。[に関する考慮事項と Web サービスの公開](../core/considerations-when-publishing-web-services.md)します。|  
|BizTalk Server プロジェクト内のメッセージ型のいずれかのユーザー定義の .NET クラスを使用してください。|メッセージの種類がグローバル アセンブリ キャッシュ (GAC) 内で参照するユーザー定義の .NET クラスを含むアセンブリをインストールする必要があります。|  
|Web クライアントが指定された資格情報を使用して、 **WindowsUser**コンテキスト プロパティですか?|公開された Web サービスの使用、Web クライアントによって指定された資格情報、 **WindowsUser**コンテキスト プロパティ。 パーティの解決は、このプロパティを使用します。 使用してパーティを設定する場合、 **WindowsUser**コンテキスト プロパティと、Web クライアントは、そのパーティに一致する資格情報で Web サービスを利用、BizTalk Server は、対応する定義済みのパーティから送信されたメッセージを識別します。 パーティの解決パイプライン コンポーネントの詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)します。|  
  
## <a name="see-also"></a>参照  
 [Web サービスの公開](../core/publishing-web-services.md)