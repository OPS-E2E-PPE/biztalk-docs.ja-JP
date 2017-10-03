---
title: "SAP システムへの接続を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9835047fd32556e6bd9f42adb768ce62f4536ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-sap-system"></a>SAP システムへの接続を作成します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスを使って、SAP システムへの通信を可能になります。 WCF では、エンドポイントのアドレスは、サービスのネットワークの場所を識別し、として、Uniform Resource Identifier () は通常表現します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムへの接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
-   チャネル ファクトリまたはチャネルを使用してリスナーを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルまたはを使用して WCF クライアントまたはサービス ホストを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。  
  
-   物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、WCF クライアント クラスまたは WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスを提供します。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
 このセクションのトピックでは、間の接続を確立する方法を記述、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]とを提供することで、SAP システム。  
  
-   接続のプロパティと、SAP 接続 URI の構造に関する情報。  
  
-   使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP システム接続 URI を作成します。](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)