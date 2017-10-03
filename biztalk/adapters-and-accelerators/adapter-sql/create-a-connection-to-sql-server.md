---
title: "SQL Server への接続を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b87b4141c9e14c680d8100a7c505dda0a0093c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-sql-server"></a>SQL Server への接続を作成します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスを使用して SQL Server データベースへの通信を可能になります。 WCF では、エンドポイントのアドレスはサービスのネットワークの場所を識別し、として、Uniform Resource Identifier ()、通常表現されます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server データベースへの接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
-   チャネル ファクトリまたは WCF チャネル モデルまたは WCF サービス モデルを使用して WCF クライアントまたはサービス ホストを作成する場合を使用してチャネル リスナーを作成します。  
  
-   物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の BizTalk Server ソリューションです。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
 このセクションのトピック間の接続を確立する方法について説明、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]および使用することによって、SQL Server データベース。  
  
-   接続のプロパティと、SQL Server 接続 URI の構造に関する情報。  
  
-   使用して接続 URI を指定する方法を説明するトピックへのリンク、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   Windows 認証を使用して SQL Server への接続に関する情報。  
  
  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)