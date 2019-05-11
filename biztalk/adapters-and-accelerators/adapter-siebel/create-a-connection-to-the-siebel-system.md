---
title: Siebel システムへの接続の作成 |Microsoft Docs
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
ms.openlocfilehash: 57704a781776fb4e16689d454e367d38fd9da0ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371762"
---
# <a name="create-a-connection-to-the-siebel-system"></a>Siebel システムへの接続を作成します。
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスで Siebel システムへの通信ができるようにします。 WCF では、エンドポイント アドレスは、サービスのネットワークの場所を識別しする Uniform Resource Identifier (URI) としては通常表現します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続プロパティを格納する、URI として、この場所を表します[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]Siebel システムへの接続を確立するために使用します。 接続 URI を指定する必要がありますとします。  
  
- チャネル ファクトリまたはを使用してチャネル リスナーを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル、またはを使用して WCF クライアントまたはサービス ホストを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。  
  
- 物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラス、または WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスです。  
  
- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- WCF クライアント クラス、または WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成するには、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用します。  
  
  このセクションのトピックでは、間の接続を確立する方法をについて説明します、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]とを提供することで Siebel システム。  
  
- 接続のプロパティ、および Siebel 接続 URI の構造について説明します。  
  
- 使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  

  
## <a name="see-also"></a>参照  
[Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)