---
title: Siebel システムへの接続を作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Siebel system
ms.assetid: 5810eeb1-6e26-4620-a731-fb352eebea2e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a108335263e85db832f4db144d27b64b92429683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-siebel-system"></a>Siebel システムへの接続を作成します。
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスを使って Siebel システムへの通信を可能になります。 WCF では、エンドポイントのアドレスは、サービスのネットワークの場所を識別し、として、Uniform Resource Identifier () は通常表現します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]Siebel システムへの接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
-   チャネル ファクトリまたはを使用してチャネル リスナーを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル、またはを使用して WCF クライアントまたはサービス ホストを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。  
  
-   物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラス、または WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスを提供します。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラス、または WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
 このセクションのトピックでは、間の接続を確立する方法を記述、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]と Siebel システムが提供することで。  
  
-   接続のプロパティと Siebel 接続 URI の構造に関する情報。  
  
-   使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  

  
## <a name="see-also"></a>参照  
[Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)