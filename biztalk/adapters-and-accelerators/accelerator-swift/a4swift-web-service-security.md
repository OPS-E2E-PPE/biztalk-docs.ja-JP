---
title: A4SWIFT Web サービスのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eca05508f9771a61f31cc648675a477f56193702
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378707"
---
# <a name="a4swift-web-service-security"></a>A4SWIFT Web サービスのセキュリティ
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安全性の高いハイブリッド セキュリティ モデルの既定の Web サービスがインストールされています。 Web サービスの間で信頼の境界が存在する IIS/ASP.NET モデルで、[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]サイト、および[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]データベース。  
  
## <a name="iis-and-aspnet-security-settings"></a>IIS と ASP.NET のセキュリティ設定  
 呼び出しはに対して行われた場合、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] IIS Web サーバーを使用してユーザーを認証する最初[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証します。 Web サービスの web.config が使用する既定で設定されて[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]、偽装を使用しない認証し、呼び出し元のメンバーであることを検証、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]ユーザー グループ。 呼び出し元のメンバーである場合、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Users グループ、Web サービス メソッドは、アプリケーション プールのプロセス id で実行されます。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]、これは、既定のアプリケーション プールを[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]します。  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービスを Web メソッドの呼び出し元の受信トレイからメッセージを削除、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービスの呼び出し元を偽装する必要があります、**削除**と**GetCheckedOutUser**メソッド。 これらは、最初の呼び出し元のコンテキストで実行メソッドのみです。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービスには、これらの Web メソッドの呼び出し元が偽装中、呼び出し元には明示的なアクセス許可が動作している呼び出し元となる SharePoint ドキュメント ライブラリの設定が必要です。  
  
## <a name="a4swift-secure-communication-settings"></a>A4SWIFT のセキュリティで保護された通信の設定  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 流れるときに、Web サービスのメッセージの機密性と整合性を保証に関心が[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]に[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]をネットワーク経由で BizTalk アプリケーションにします。 最高レベルのセキュリティを提供する[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アプリケーション間のセキュリティで保護された通信の 2 つのレベルをサポートしています: トランスポート レベルとメッセージ レベル。  
  
## <a name="transport-level-security"></a>トランスポート レベルのセキュリティ  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 間の SSL 通信をサポートしている[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web サービス、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] メッセージを送信するときに、MRSR サイトのセキュリティ設定を自動的に適応します。  
  
 インターネット プロトコル セキュリティ (IPSec) は、セキュリティで保護された通信を実装することも[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]します。  
  
 間の通信をセキュリティで保護された IPSec の実装の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]、"セキュリティで保護する、展開の BizTalk Server"で BizTalk Server のヘルプを参照してください。  
  
  
## <a name="message-level-security"></a>メッセージ レベルのセキュリティ  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] メッセージ レベルのセキュリティは、デジタル署名付きメッセージの整合性を提供することによって実現されます。 メッセージ署名[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]の詳細については[InfoPath セキュリティ](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)します。