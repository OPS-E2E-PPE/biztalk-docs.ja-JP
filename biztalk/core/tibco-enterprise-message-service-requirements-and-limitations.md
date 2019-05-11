---
title: TIBCO Enterprise Message Service の要件と制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a0adbc67dfb78eef97876d65b4da50a343efce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379842"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a>TIBCO Enterprise Message Service の要件と制限事項

## <a name="system-requirements"></a>システム要件  
含まれている TIBCO Enterprise Message Service にはクライアント SDK (TIBCO EMS c# API を使用) が含まれています。 BizTalk Adapter for TIBCO EMS では、この API を使用して、TIBCO EMS と通信します。  
  
## <a name="add-the-api-to-the-gac"></a>API を GAC に追加します。  
 BizTalk Adapter for TIBCO EMS は、TIBCO EMS を必要とC#API, TIBCO します。EMS.dll、グローバル アセンブリ キャッシュ (GAC) に追加します。 アダプターは、例外をトリガーし、このアセンブリがインストールされていない場合、適切なメッセージを記録します。  
  
1. コピーに TIBCO EMS C# #API、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
2. ディレクトリの場所を変更、 C# API ファイルで TIBCO します。EMS します。DLL です。  
  
    既定のインストールでは、この DLL へのパスは、c:\tibco\ems\clients\cs\TIBCO が。EMS します。DLL です。  
  
3. コマンド プロンプトで次のように入力します。  
  
    `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
    TIBCO します。EMS.dll GAC が表示されるようになりました。  
  
    コントロール パネルの [GAC の一覧を表示、開く**管理ツール**オープン**Microsoft .NET Framework x.xconfiguration]**、順にクリックします**アセンブリ キャッシュ**します。  
  
## <a name="limitations"></a>制限事項  
 BizTalk Adapter for TIBCO Enterprise Message Service は、TIBCO を使用します。TIBCO Enterprise Message Service との通信に EMS.dll します。 TIBCO EMS を使用すると、次の制限を考慮する必要がありますC#API:  
  
-   メッセージの圧縮は、TIBCO EMS クライアントで EMS に圧縮形式でメッセージを送信できるようにがで使用できない、 C# API。  
  
-   アダプターとサーバー間のメッセージの暗号化では使用できない、 C# API。 C# OpenSSL ライブラリを使用して SSL 暗号化 API は許可されません。  
  
-   C# API が EMS 用の管理 API をサポートしていません。  
  
-   サイズが 50 MB を超えるメッセージは送信できませんまたは BizTalk TIBCO EMS アダプターを使用して受信します。 環境では、このサイズを超えた System.OutOfMemoryException 例外が発生します。  
  
## <a name="see-also"></a>参照  
 [計画および設計](../core/planning-and-architecture16.md)