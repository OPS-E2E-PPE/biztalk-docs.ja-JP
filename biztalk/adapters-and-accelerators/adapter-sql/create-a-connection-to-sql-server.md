---
title: SQL Server への接続の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf9a791ba404f1890becc81cfcc545df2cb3f78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369888"
---
# <a name="create-a-connection-to-sql-server"></a>SQL Server への接続を作成します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスを使用して SQL Server データベースへの通信ができるようにします。 WCF は、エンドポイント アドレスは、サービスのネットワークの場所を識別しする Uniform Resource Identifier (URI) として、通常表現されます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続プロパティを格納する、URI として、この場所を表します[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server データベースへの接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
- チャネル ファクトリまたは WCF チャネル モデルまたは WCF サービス モデルを使用して WCF クライアントまたはサービス ホストを作成する場合を使用してチャネル リスナーを作成します。  
  
- 物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の BizTalk Server ソリューションです。  
  
- WCF クライアント クラスまたは WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成するには、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用します。  
  
  このセクションのトピックでは、間の接続を確立する方法をについて説明します、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]とを提供することで、SQL Server データベース。  
  
- 接続のプロパティと、SQL Server の接続 URI の構造について説明します。  
  
- 使用して接続 URI を指定する方法を説明するトピックへのリンク、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- Windows 認証を使用して SQL Server への接続について説明します。  
  
  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)