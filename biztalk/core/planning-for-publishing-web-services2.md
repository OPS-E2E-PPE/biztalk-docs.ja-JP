---
title: Web Services2 を公開するための計画 |Microsoft ドキュメント
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
ms.openlocfilehash: 9d0b9d593a3309f7b4477f2fa735f7e265b614c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264458"
---
# <a name="planning-for-publishing-web-services"></a>Web サービスを公開するための計画
Web サービスは、オーケストレーション内からアクセスできます。 BizTalk Web サービス公開ウィザードを使用して、Web サービスを公開することもできます。  
  
 次の表は、Web サービスを計画するときに検討する必要がある項目を示しています。  
  
|計画段階の考慮事項|推奨|  
|-----------------------|--------------------|  
|BizTalk Server プロジェクトがビルドされているか|BizTalk Web サービス公開ウィザードを実行する前に、BizTalk Server プロジェクトをビルドする必要があります。|  
|システムで Web サービスの実行が有効になっているか|BizTalk Web サービス公開ウィザードを実行する前に、コンピュータで Web サービスを有効にする必要があります。 Web サービスには、システムを有効にする方法の詳細については、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。|  
|有効な XML 文字および要素のみがスキーマに含まれているか|Web サービスは、中国語、日本語、韓国語 (CJK) 統合漢字拡張 A 文字をサポートしません。 一部の XML スキーマ (XSD) 要素にも、この制限があります。 有効な XML 文字とサポートされている要素および要素に関する考慮事項に関する詳細については、次を参照してください。[に関する考慮事項と Web サービスの公開](../core/considerations-when-publishing-web-services.md)です。|  
|BizTalk Server プロジェクトのメッセージの種類でユーザー定義の .NET クラスを使用しているか|メッセージの種類で参照しているユーザー定義の .NET クラスを含むアセンブリを、グローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。|  
|Web クライアントがの指定された資格情報を使用して、 **WindowsUser**コンテキスト プロパティですか?|公開された Web サービスの使用を消費する Web クライアントから提供された資格情報、 **WindowsUser**コンテキスト プロパティです。 パーティの解決では、このプロパティを使用します。 使用してパーティを設定した場合、 **WindowsUser**コンテキスト プロパティと、Web クライアントは、そのパーティに一致する資格情報で Web サービスを利用する、BizTalk Server が、対応する定義済みのパーティから送信されたメッセージを識別します。 パーティの解決パイプライン コンポーネントの詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。|  
  
## <a name="see-also"></a>参照  
 [Web サービスの公開](../core/publishing-web-services.md)