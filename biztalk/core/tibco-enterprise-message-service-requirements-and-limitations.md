---
title: TIBCO Enterprise Message Service の要件と制限事項 |Microsoft ドキュメント
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
ms.openlocfilehash: fcd386245ba06c2e3b5a5b92df7b7a7f01a1a749
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013673"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a>TIBCO Enterprise Message Service の要件と制限事項

## <a name="system-requirements"></a>システム要件  
含まれている TIBCO Enterprise Message Service には、クライアント SDK (TIBCO EMS c# API を使用) が含まれています。 BizTalk Adapter for TIBCO EMS は、この API を使用して TIBCO EMS とやり取りします。  
  
## <a name="add-the-api-to-the-gac"></a>API を GAC に追加します。  
 BizTalk Adapter for TIBCO EMS では、TIBCO EMS C# API である TIBCO.EMS.dll をグローバル アセンブリ キャッシュ (GAC) に追加する必要があります。 このアセンブリがインストールされていない場合、アダプターは例外をトリガーし、適切なメッセージを記録します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに TIBCO EMS C# API をコピーします。  
  
2.  C# API ファイルである TIBCO.EMS.DLL の場所にディレクトリを変更します。  
  
     既定のインストールでは、この DLL へのパスは c:\tibco\ems\clients\cs\TIBCO.EMS.DLL です。  
  
3.  コマンド プロンプトで、次のように入力します。  
  
     `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
     TIBCO.EMS.dll に GAC が表示されるようになります。  
  
     コントロール パネルの [GAC の一覧を表示、開く**管理ツール**、開かれている**Microsoft .NET Framework x.xconfiguration]**、クリックして**アセンブリ キャッシュ**です。  
  
## <a name="limitations"></a>制限事項  
 BizTalk Adapter for TIBCO Enterprise Message Service は、TIBCO.EMS.dll を使用して TIBCO Enterprise Message Service とやり取りします。 TIBCO EMS C# API を使用するときは、次の制限事項を考慮する必要があります。  
  
-   この C# API では、メッセージ圧縮 (TIBCO EMS クライアントが EMS に圧縮形式でメッセージを送信できるようにします) は使用できません。  
  
-   この C# API では、アダプターとサーバーの間でメッセージを暗号化することはできません。 この C# API では、OpenSSL ライブラリを使用した SSL 暗号化は許可されません。  
  
-   この C# API は、EMS 用の管理 API をサポートしません。  
  
-   BizTalk TIBCO EMS アダプターを使用して、50 MB を超えるサイズのメッセージを送受信することはできません。 このサイズを超えた場合、System.OutOfMemoryException 例外が発生します。  
  
## <a name="see-also"></a>参照  
 [計画および設計](../core/planning-and-architecture16.md)