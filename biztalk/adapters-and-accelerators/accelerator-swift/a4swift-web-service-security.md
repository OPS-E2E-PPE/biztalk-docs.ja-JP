---
title: "A4SWIFT Web サービス セキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IIS security
- Web service [A4SWIFT]
- security, transport-level security
- security, message-level security
- ASP.NET security
- A4SWIFT, Web service
- A4SWIFT, security
- security, IIS
- security, ASP.NET
- security, Web service
- messages, security
ms.assetid: e6c7d275-569f-47f6-81fb-10bcd86ff417
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8510172517d58475d855d258b72b16271835dbc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a4swift-web-service-security"></a>A4SWIFT Web サービスのセキュリティ
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安全性の高いハイブリッド セキュリティ モデルの既定の Web サービスがインストールされています。 Web サービスの間で信頼の境界が存在する IIS/ASP.NET モデルで、[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]サイト、および[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]データベース。  
  
## <a name="iis-and-aspnet-security-settings"></a>IIS と ASP.NET のセキュリティ設定  
 呼び出しが行われたときに、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] IIS Web サーバーを使用してユーザーを認証する最初[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証します。 Web サービスの web.config は既定で使用する設定[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]偽装、なしで認証に、呼び出し元のメンバーであることを検証し、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]ユーザー グループ。 呼び出し元のメンバーである場合、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Users グループ、Web サービス メソッドは、アプリケーション プールのプロセス id で実行されます。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]、これは、既定のアプリケーション プールの[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]します。  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービスを Web メソッドの呼び出し元の受信トレイからメッセージを削除、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービスの呼び出し元を偽装する必要があります、**削除**と**GetCheckedOutUser**メソッド。 これらは、最初の呼び出し元のコンテキストで実行する唯一の方法です。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービスはこれらの Web メソッドの呼び出し元を偽装して、呼び出し元には、明示的なアクセス許可が呼び出し元が機能する基になるは、SharePoint ドキュメント ライブラリに設定します。  
  
## <a name="a4swift-secure-communication-settings"></a>A4SWIFT のセキュリティで保護された通信の設定  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]整合性と Web サービスのメッセージの機密性を確保しから流れるとき[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]に[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]をネットワーク経由で BizTalk アプリケーションにします。 最高レベルのセキュリティを提供する[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アプリケーション間でセキュリティで保護された通信の 2 つのレベルをサポートしています: トランスポート レベルとメッセージ レベルです。  
  
## <a name="transport-level-security"></a>トランスポート レベルのセキュリティ  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]間で SSL 通信をサポートする[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービス、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]メッセージを送信するときに、MRSR サイトのセキュリティ設定を自動的に適応します。  
  
 間のセキュリティで保護された通信にインターネット プロトコル セキュリティ (IPSec) を実装することも[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]です。  
  
 IPSec の実装との間の通信を保護するための詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]、「セキュリティで保護する展開の BizTalk Server」を参照してください[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。  
  
  
## <a name="message-level-security"></a>メッセージ レベルのセキュリティ  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]メッセージ レベルのセキュリティは、整合性を提供するメッセージにデジタル署名によって実現されます。 メッセージ署名[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]で詳しく説明[InfoPath セキュリティ](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)です。