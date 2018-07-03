---
title: SAP システムへの接続の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef25dddf3d30f584b30aa0f35b8b1c4140d285e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965811"
---
# <a name="create-a-connection-to-the-sap-system"></a>SAP システムへの接続を作成します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスからの SAP システムに通信できます。 WCF では、エンドポイント アドレスは、サービスのネットワークの場所を識別しする Uniform Resource Identifier (URI) としては通常表現します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続プロパティを格納する、URI として、この場所を表します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムへの接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
- チャネル ファクトリまたはを使用してチャネル リスナーを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルまたはを使用して WCF クライアントまたはサービス ホストを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。  
  
- 物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスです。  
  
- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- WCF クライアント クラスまたは WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成するには、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用します。  
  
  このセクションのトピックでは、間の接続を確立する方法をについて説明します、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]とを提供することで、SAP システム。  
  
- 接続のプロパティと、SAP 接続 URI の構造について説明します。  
  
- 使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP システム接続 URI を作成します。](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)