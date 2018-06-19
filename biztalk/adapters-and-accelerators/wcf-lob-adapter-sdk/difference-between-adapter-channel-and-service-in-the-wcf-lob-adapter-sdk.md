---
title: WCF LOB Adapter SDK のアダプタのチャネルとサービス間の相違 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24d41d96-0ea1-4a97-bd45-b65afdbbd923
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e377568887d3d626e288fc47f82714b189d44b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225010"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK のアダプタのチャネルとサービス間の相違
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]各提供一連の Api を使用して、同じコンピューター上またはネットワーク経由でアプリケーションを使用するアプリケーションの機能を公開することができます。 最も適切なフレームワークを選択するには、公開されている機能のビジネス要件および公開する対象のシステム アプリケーションのプロパティを考慮する必要があります。 このトピックでは、適切なフレームワークを選択する際のガイドラインを提供します。  
  
## <a name="when-to-write-an-adapter"></a>アダプターを記述する場合  
 使用するアダプターを作成する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とき。  
  
-   対象システムでは、既存の非*Web サービスに対応した*システム  
  
-   ターゲット システムは、動的で、新しい操作を拡張することができます。  
  
-   ターゲット システムに大量のメタデータ  
  
-   大規模な多様なユーザー数が、ターゲット システムのデータがあります。  
  
-   消費するアプリケーションには、リッチ アプリケーション メタデータ検出機能が必要があります。  
  
 たとえば、ターゲット システムには、何百もの医療費の請求を管理するための操作が含まれ、操作は、動的な場合 (つまり、ユーザーは、その他のタスクを実行する新しい操作を追加できます)、理にかなって、を使用してこの機能を公開する[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. 新しい操作が、アダプターを使用してアプリケーションが探索可能であるようになります。 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]が静的であるため、サービス コントラクトを変更する必要があります。  
  
## <a name="when-to-write-a-service"></a>サービスを記述する場合  
 使用して、 *WCF サービス モデル*サービスを作成するとき。  
  
-   ターゲット システムは静的であり、固定の一連の操作  
  
-   ターゲット システムがまったくまたはほとんどのメタデータ  
  
-   サービス開発者が公開するアプリケーションの知識の詳細な  
  
-   まったく新しいアプリケーションを公開します。  
  
-   汎用的なトランスポート アダプターを作成します。  
  
 たとえば、ターゲット システムにスポーツ チームを管理するための 20 の操作が含まれている場合を使用して、静的なコントラクトと操作を公開できます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。 これにより、メタデータの不要な機能を実装することを回避して、開発時間を最小化できる可能性があります。  
  
## <a name="when-to-write-a-channel"></a>チャネルを記述する場合  
 使用して、 *WCF チャネル モデル*チャネルを作成するとき。  
  
-   ワイヤ プロトコルを作成します。 ワイヤ プロトコルの例には、Ws-reliablemessaging プロトコルが含まれます。  
  
-   送信/受信 WCF メッセージ (TCP、HTTP、名前付きパイプ、MSMQ および PeerChannel) WCF に含まれているもの以外のトランスポートを経由します。 たとえば、UDP トランスポート、TIBCO、または Java メッセージング Service (JMS) トランスポートを記述することができます。  
  
-   Web サービスとして公開されず、システムと統合します。  ここでは、トランスポートは、既存のシステムと直接対話する既存のシステムのメッセージの形式または WCF クライアントを許可する API を WCF メッセージを適応させるアダプターとして機能します。 この例は、Web Services Enhancement (WSE) 3.0 TCP トランスポートです。  
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [WCF LOB Adapter SDK を使用して LOB システムを理解します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)