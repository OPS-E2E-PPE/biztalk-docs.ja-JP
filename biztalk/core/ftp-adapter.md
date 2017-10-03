---
title: "FTP アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FTP adapters
ms.assetid: 878dc0b0-d1d8-405a-a697-654dd18ba08e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc72b5166f8971392b41f275338bde593d325af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ftp-adapter"></a>FTP アダプタ
FTP アダプターを使用すると、FTP サーバーと Microsoft BizTalk Server の間でデータを交換できます。これにより、基幹業務アプリケーションを搭載したさまざまなプラットフォームに保存されている重要なデータを統合できます。 アダプターは、SOCKS4 経由で FTP サーバーまたは SOCKS5 プロキシ サーバーに接続できます。  
  
 FTP アダプターでは、FTP サーバーから BizTalk Server に多数のファイルを送信できます。 また、ファイルをオーケストレーションの一部として送信できます。  
  
 FTP アダプターは、2 つのアダプターで構成されます: 受信アダプタと送信アダプター。  

このセクションでは、FTP 受信アダプタと FTP 送信アダプタ、およびセキュリティとベスト プラクティス情報について説明します。  
  
 ## <a name="receive-adapter"></a>受信アダプター  
  
 FTP 受信アダプターを使用すると、FTP サーバーから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にデータを移動できます。 主な機能は次のとおりです。  
  
-   要求時に FTP サーバーからファイルを取得します。  
  
-   構成可能なスケジュールに基づいてポーリングを実行しています。  
  
-   FTP サーバーにポーリングし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にデータを直接送信します。  
  
-   FTP サーバーを IP アドレス、ポート、パスワード、およびホスト名で指定します。  
  
-   ファイルの配信の保証  
  
     また、FTP 受信アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールおよび BizTalk エクスプローラーと連動し、各受信機能を構成および管理します。この機能は、次の構成項目で構成されます。  
  
-   FTP コマンドを実行するためのポーリング間隔 (例、60 分)  
  
-   ドキュメントを特定の BizTalk 送信ポートまたは受信場所にルーティングする際に使用する情報  
  
> [!NOTE]
>  FTP 受信アダプターは、パーティション分割されたデータ セットからのファイルの受信をサポートしていません。  
  
## <a name="send-adapter"></a>送信アダプター  
  
 FTP 送信アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から FTP サーバーにデータを移動できます。 主な機能は次のとおりです。  
  
-   要求時に送信を実行する機能  
  
-   配信の保証  
  
## <a name="supported-platforms"></a>サポートされているプラットフォーム  
次のプラットフォームのいずれかを FTP サーバーに格納されている情報にアクセスします。  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)] 2016

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)] R2
  
-   [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
-   [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2008  
  
-   [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2000 Service Pack 3 (SP3) 以降  
  
-   Sun Solaris 9.0  
  
-   HP-UX  
  
-   Linux (Redhat 7.x)  
  
-   IBM z/OS v1.9 (MVS)  
  
-   MVS を実行している IBM O/S 390  
  
-   AS/400 OS/400 V5R1  
  
-   i5/OS V5R4 (AS400)  
  
-   i5/OS V6R1 (AS400)  
  
-   GXS ICS  
  
-   AIX  
  
 サービス パックが特に記載されていない限り、すべてのサービス パックがサポートされます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
[ベスト プラクティスと、FTP アダプターの推奨事項](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[FTP アダプターの構成](../core/configuring-the-ftp-adapter.md)  

[FTP アダプター プロパティ スキーマおよびプロパティ](../core/ftp-adapter-property-schema-and-properties.md)