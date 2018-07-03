---
title: '手順 7: BizTalk HTTP フロント エンド サーバーの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b6429ba6c753bac16874fd6fa81e13e91927b58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989187"
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a>手順 7: BizTalk HTTP フロント エンド サーバーの構成
このセクションで Web サーバーの構成のガイドラインを提供します、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]展開します。  
  
> [!NOTE]
>  1 台のコンピューターの展開では、このコンピューターは、もう 1 つは、メッセージング処理と同じコンピューターは。  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a>BizTalk HTTP フロント エンド サーバーを構成するには  
  
1. インターネット インフォメーション サービス (IIS) のインストールと ASP.NET です。  
  
2. IIS マネージャーを開き、選択**Web サービス拡張**します。 ASP.NET 1.1 および ASP.NET v2.0 に設定されていることを確認**許可**します。  
  
3. いることを確認、**メッセージ キュー**サービス (MSMQ) と**ルーティング サポート**から追加/削除がインストールされている[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー/メッセージ キューの下のコンポーネント。  
  
4. 追加/削除 でネットワーク DTC アクセスが有効であることを確認[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバーのカテゴリの下にあるコンポーネント。 ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。  
  
5. 」の説明に従って、展開に Secure Sockets Layer (SSL) プロトコルを実装[サポート Secure Sockets Layer (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)します。  
  
6. インストールし、Windows SharePoint Services 3.0 SP1 を構成します。  
  
7. インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[BizTalk Accelerator for SWIFT を HTTP フロント エンド サーバー上に構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)します。  
  
   このセクションには、次のトピックが含まれています。  
  
-   [Secure Sockets Layer (SSL) のサポート](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [インストールして、BizTalk HTTP フロント エンド サーバーを構成します。](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [HTTP フロントエンド サーバーに BizTalk Accelerator for SWIFT をインストールして構成する](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)