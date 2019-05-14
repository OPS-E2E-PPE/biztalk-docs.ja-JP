---
title: WCF LOB Adapter SDK アダプター チャネルとサービス間の相違 |Microsoft Docs
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
ms.openlocfilehash: e7ec63ce59139d0a34aa66969bde1898c0981e94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363676"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK のアダプターのチャネルとサービス間の違い
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]アプリケーション機能を使用する同じコンピューター上またはネットワーク経由でアプリケーションを公開するために使用できる Api のセットを提供します。 最適なフレームワークを選択するには、公開されている機能のビジネス要件および公開する対象のシステム アプリケーションのプロパティを考慮する必要があります。 このトピックでは、適切なフレームワークを選択する際のガイドラインを提供します。  
  
## <a name="when-to-write-an-adapter"></a>アダプターを記述する場合  
 アダプターを使用して、書き込むことを検討、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とき。  
  
- 対象システムでは、既存の非*Web サービスが有効な*システム  
  
- ターゲット システムは動的であり新しい操作を使用して拡張できます。  
  
- ターゲット システムに大量のメタデータ  
  
- 大規模で多様なユーザー数が、ターゲット システムのデータがあります。  
  
- コンシューマー側アプリケーションには、メタデータ検出機能の豊富なアプリケーションが必要があります。  
  
  たとえば、ターゲット システムには、何百も医療の要求を管理するための操作にはが含まれています操作は、動的な場合 (つまり、ユーザーは、追加のタスクを実行する新しい操作を追加できます)、理にかなって、を使用してこの機能を公開[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. 新しい操作が、アダプターを使用してアプリケーションが検出可能であるようになります。 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、Static であるために、サービス コントラクトを変更する必要があります。  
  
## <a name="when-to-write-a-service"></a>サービスを記述する場合  
 使用して、 *WCF サービス モデル*サービスを作成するとき。  
  
- ターゲット システムは静的であり、操作の固定セットがあります。  
  
- ターゲット システムがほとんどまたはまったくないメタデータ  
  
- サービス開発者は、公開するアプリケーションの知識の詳細な  
  
- 新しいアプリケーションが公開されています。  
  
- 汎用的なトランスポート アダプターを作成します。  
  
  たとえば、ターゲット システムにスポーツ チームを管理するための 20 の操作が含まれている場合を使用して静的なコントラクトと操作を公開できます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]します。 これにより、不要なメタデータ機能を実装して、開発時間を最小化できる可能性があります。  
  
## <a name="when-to-write-a-channel"></a>チャネルを記述する場合  
 使用して、 *WCF チャネル モデル*チャネルを作成するとき。  
  
-   ワイヤ プロトコルを作成します。 ワイヤ プロトコルの例では、WS-ReliableMessaging プロトコルを示します。  
  
-   送信/受信 WCF メッセージ (TCP、HTTP、名前付きパイプ、MSMQ および PeerChannel) WCF に含まれているもの以外のトランスポートを経由します。 たとえば、UDP トランスポート、TIBCO、または Java メッセージング Service (JMS) トランスポートを記述することができます。  
  
-   Web サービスとして公開されているシステムと統合します。  この場合、トランスポートは、既存のシステムと直接対話する既存システムのメッセージ形式または API を WCF クライアントを許可するための WCF メッセージを適合させるアダプターとして機能します。 この例は、Web サービス拡張 (WSE) 3.0 の TCP トランスポートです。  
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [WCF LOB Adapter SDK を使用して LOB システムを理解します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)