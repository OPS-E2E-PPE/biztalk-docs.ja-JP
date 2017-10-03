---
title: "手順 7: BizTalk HTTP フロント エンド サーバーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5840099816149265711744373e08d3a9a9d91cd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a>手順 7: BizTalk HTTP フロント エンド サーバーを構成します。
このセクションは、Web サーバーの構成のガイドラインを示します、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]展開します。  
  
> [!NOTE]
>  1 台のコンピューター展開では、このコンピューターは、1 つのメッセージングを行うと処理と同じコンピューターは。  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a>BizTalk HTTP フロント エンド サーバーを構成するには  
  
1.  インターネット インフォメーション サービス (IIS) のインストールと ASP.NET です。  
  
2.  IIS マネージャーを開き、選択**Web サービス拡張**です。 ASP.NET v1.1 と、ASP.NET 2.0 に設定されるように**許可**です。  
  
3.  いることを確認、**メッセージ キュー**サービス (MSMQ) と**ルーティング サポート**を追加/削除 からインストール[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー/メッセージ キューの下のコンポーネントです。  
  
4.  追加/削除 でネットワーク DTC アクセスが有効になっていることを確認[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー カテゴリの下にあるコンポーネント。 ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。  
  
5.  」の説明に従って、展開に Secure Sockets Layer (SSL) プロトコルを実装[サポート (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)です。  
  
6.  インストールし、Windows SharePoint Services 3.0 SP1 を構成します。  
  
7.  インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[BizTalk Accelerator for SWIFT HTTP フロント エンド サーバー上に構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [Secure Sockets Layer (SSL) をサポートします。](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [インストールして、BizTalk HTTP フロント エンド サーバーを構成します。](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [インストールと BizTalk Accelerator を HTTP フロント エンド サーバーに SWIFT の構成](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)