---
title: FTP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FTP adapters
ms.assetid: 878dc0b0-d1d8-405a-a697-654dd18ba08e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96890b0778e5e7c0684e1e5e326f245460487dd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345295"
---
# <a name="ftp-adapter"></a>FTP アダプター
FTP アダプターは、FTP サーバーと Microsoft BizTalk Server の間でデータを交換しのさまざまな基幹業務アプリケーションとプラットフォームに格納されている重要なデータを統合できます。 アダプターは、SOCKS4 経由での FTP サーバーまたは SOCKS5 プロキシ サーバーに接続できます。  
  
 FTP アダプターは、FTP サーバーから BizTalk Server の多数のファイルを転送できます。 ファイルは、オーケストレーションの一部としてそのも転送できます。  
  
 FTP アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。  

このセクションの説明、FTP 受信し、送信アダプター、およびセキュリティとベスト プラクティスの情報。  
  
 ## <a name="receive-adapter"></a>受信アダプター  
  
 FTP 受信アダプターを使用する FTP サーバーからデータを移動する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 主な機能は次のとおりです。  
  
- 必要に応じて、FTP サーバーからファイルを取得します。  
  
- 構成可能なスケジュールに基づいてポーリングを実行しています。  
  
- FTP サーバーにポーリングし、データに直接送信します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- IP アドレス、ポート、パスワード、およびホスト名として FTP サーバーを指定します。  
  
- ファイルの配信を保証  
  
   また、FTP 受信アダプターとの連携、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールと BizTalk エクスプローラを構成および管理する各受信関数で、次の構成項目で構成されます。  
  
- FTP コマンド (たとえば、60 分) を実行するポーリング間隔  
  
- 特定の BizTalk へのドキュメントをルーティングする際に使用して情報の送信ポートまたは受信場所  
  
> [!NOTE]
>  FTP 受信アダプタは、パーティション分割されたデータ セットからのファイルの受信をサポートしていません。  
  
## <a name="send-adapter"></a>送信アダプター  
  
 FTP 送信アダプタからデータを移動することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]FTP サーバーにします。 主な機能は次のとおりです。  
  
-   オンデマンドで送信を実行するには  
  
-   保証された配信  
  
## <a name="supported-platforms"></a>サポートされているプラットフォーム  
FTP サーバーに、次のプラットフォームのいずれかに格納されている情報にアクセスします。  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)] 2016

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)] R2
  
- [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
- [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2008  
  
- [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2000 Service Pack 3 (SP3) 以降  
  
- Sun Solaris 9.0  
  
- HP-UX  
  
- LINUX (Redhat 7.x)  
  
- IBM Z/OS v1.9 (MVS)  
  
- MVS を実行している IBM O/S 390  
  
- AS/400 OS/400 V5R1  
  
- OS/i5 V5R4 (AS400)  
  
- OS/i5 V6R1 (AS400)  
  
- GXS ICS  
  
- AIX  
  
  サービス パックが具体的にはされている場合を除き、すべてのサービス パックがサポートされます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
[FTP アダプターのベスト プラクティスと推奨事項](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[FTP アダプターの構成](../core/configuring-the-ftp-adapter.md)  

[FTP アダプター プロパティ スキーマおよびプロパティ](../core/ftp-adapter-property-schema-and-properties.md)